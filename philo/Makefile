NAME = philo
CFLAGS = -g
#CFLAGS = -Wall -Wextra -Werror -g

RM = rm -rf
CC = cc
AR = ar rc

HEADER = -I ./include/

# *** source code files *** #
SRC_PATH = src/
SRC = \
		main.c \

SRCS := $(addprefix $(SRC_PATH), $(SRC))

# *** Intro Msg *** #



# *** object files *** #
OBJ_PATH = obj/
OBJ = $(SRC:.c=.o)
OBJS = $(addprefix $(OBJ_PATH), $(OBJ))

all: ${NAME} intro_msg

intro_msg:
	@$(info ===============================================)
	@$(info Philosophers compiled successfully)
	@$(info ===============================================)
	@$(info Input arguments:)
	@$(info )
	@$(info number_of_philosophers / [ms])
	@$(info time_to_die / [ms])
	@$(info time_to_eat / [ms])
	@$(info time_to_sleep / [ms])
	@$(info -----------------------------------------------)
	@$(info Optional argument:)
	@$(info )
	@$(info number_of_times_each_philosopher_must_eat / [ms])
	@$(info ===============================================)
	@$(info )

${OBJ_PATH}%.o: ${SRC_PATH}%.c
	@${CC} ${CFLAGS} -c $< $(HEADER) -o $@

${OBJS}: ${OBJ_PATH}

${OBJ_PATH}:
	@mkdir ${OBJ_PATH}

${NAME}: ${OBJS}
	@${CC} -o ${NAME} ${OBJS}

# *** general rules *** #
clean:
	@${RM} ${OBJ}

fclean: clean
	${RM} ${NAME}

re: fclean all

.PHONY: all clean fclean re

# ls *.c | sed 's/$/ \\/'