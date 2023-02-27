NAMESERVER = server
NAMECLIENT = client
NAME_SVR_BONUS = server_bonus
NAME_CLT_BONUS = client_bonus

LIB = ./ft_printf/libftprintf.a

SRCSERVER = server.c
SRCCLIENT = client.c
SRCSERVER_BONUS = server_bonus.c
SRCCLIENT_BONUS = client_bonus.c

FLAGS = -Wall -Wextra -Werror
CC = gcc
OBJSERVER = $(SRCSERVER:.c=.o)
OBJCLIENT = $(SRCCLIENT:.c=.o)
SRCS_SVR_BONUS_OBJS = $(SRCSERVER_BONUS:.c=.o)
SRCS_CLT_BONUS_OBJS = $(SRCCLIENT_BONUS:.c=.o)


all : $(LIB) $(NAMESERVER) $(NAMECLIENT)

$(LIB):
	make -C ./ft_printf

$(NAMESERVER) : $(OBJSERVER)
	$(CC) $(OBJSERVER) -o $(NAMESERVER) $(LIB)

$(NAMECLIENT) : $(OBJCLIENT)
	$(CC) $(OBJCLIENT) -o $(NAMECLIENT) $(LIB)

$(NAME_SVR_BONUS) : $(SRCS_SVR_BONUS_OBJS)
	$(CC) $(SRCS_SVR_BONUS_OBJS) -o $(NAME_SVR_BONUS) $(LIB)

$(NAME_CLT_BONUS) : $(SRCS_CLT_BONUS_OBJS)
	$(CC) $(SRCS_CLT_BONUS_OBJS) -o $(NAME_CLT_BONUS) $(LIB)


bonus: $(LIB) $(NAME_CLT_BONUS) $(NAME_SVR_BONUS)

clean:
	rm -rf $(OBJSERVER) $(OBJCLIENT)

fclean: clean
	rm -rf $(NAMESERVER) $(NAMECLIENT)

clean_bonus:
	rm -rf $(SRCS_SVR_BONUS_OBJS) $(SRCS_CLT_BONUS_OBJS)

fclean_bonus: clean_bonus
	rm -rf $(NAME_SVR_BONUS) $(NAME_CLT_BONUS)


ffclean: fclean
	make fclean -C ./ft_printf

allclean: fclean fclean_bonus ffclean

re:fclean all

re_bonus: fclean_bonus bonus

.PHONY : bonus clean fclean clean_bonus fclean_bonus ffclean re re_bonus allclean