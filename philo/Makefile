# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: cbridget <cbridget@student.21-school.ru    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2022/01/05 19:40:05 by cbridget          #+#    #+#              #
#    Updated: 2022/04/25 12:11:46 by cbridget         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME = philo

HEAD = hdrs/philosophers.h

SRC = philosophers.c parser.c parser2.c ph_threads.c ph_utils.c

OBJ = $(addprefix obj/,$(SRC:.c=.o))

BUILD_FOLDER := $(shell mkdir -p obj)

FLAGS = -Wall -Werror -Wextra

CC = cc

.PHONY : all clean fclean re

all : $(NAME)

$(NAME) : $(OBJ)
	$(CC) $(FLAGS) $(OBJ) -o $(NAME)

obj/%.o : src/%.c $(HEAD) Makefile
	$(CC) $(FLAGS) -iquote hdrs -c $< -o $@

clean :
	rm -rf obj

fclean : clean
	rm -f $(NAME)

re : fclean
	@mkdir -p obj
	$(MAKE)
