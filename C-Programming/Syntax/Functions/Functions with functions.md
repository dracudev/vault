In C programming, functions can be passed as parameters to other functions using function pointers. This technique allows for flexible and dynamic behavior, enabling functions to operate on other functions.

A function pointer in C holds the address of a function. It allows indirect invocation of a function through its pointer.

```c
return_type (*function_pointer_name)(parameter_list);

char	*ft_strmapi(char const *s, char (*f)(unsigned int, char))
{
	unsigned int	i;
	char			*result;

	if (s == NULL)
		return (NULL);
	i = 0;
	result = (char *)malloc(sizeof(char) * (ft_strlen(s) + 1));
	if (result == NULL)
		return (NULL);
	while (s[i])
	{
		result[i] = (f)(i, s[i]);
		i++;
	}
	result[i] = '\0';
	return (result);
}

char to_upper(unsigned int i, char c)
{
		
		if (c >= 'a' && c <= 'z')
			c -= 32;
		return (c);
}

int	main(void)
{
	char *str;

	str = "abcedef";
	printf("%s", ft_strmapi(str, to_upper))); 
}
```