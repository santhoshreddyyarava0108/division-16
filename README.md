# division-16
org 100h

mov ax,1234h
mov bx,0056h
div bx
mov cx,ax
mov dx,dx

and ax,0F000h
shr ax,12
add ax,30h
cmp ax,39h
jle print_first_digit
add ax,7

print_first_digit:
    mov dl,al
    mov ah,02h
    int 21h

mov ax,cx
and ax,0F00h
shr ax,8
add ax,30h
cmp ax,39h
jle print_second_digit
add ax,7

print_second_digit:
    mov dl,al
    mov ah,02h
    int 21h

mov ax,cx
and ax,0F0h
shr ax,4
add ax,30h
cmp ax,39h
jle print_third_digit
add ax,7

print_third_digit:
    mov dl,al
    mov ah,02h
    int 21h

mov ax,cx
and ax,0Fh
add ax,30h
cmp ax,39h
jle print_fourth_digit
add ax,7

print_fourth_digit:
    mov dl,al
    mov ah,02h
    int 21h

mov ax,dx
and ax,0F000h
shr ax,12
add ax,30h
cmp ax,39h
jle print_first_rem_digit
add ax,7

print_first_rem_digit:
    mov dl,al
    mov ah,02h
    int 21h

mov ax,dx
and ax,0F00h
shr ax,8
add ax,30h
cmp ax,39h
jle print_second_rem_digit
add ax,7

print_second_rem_digit:
    mov dl,al
    mov ah,02h
    int 21h

mov ax,dx
and ax,0F0h
shr ax,4
add ax,30h
cmp ax,39h
jle print_third_rem_digit
add ax,7

print_third_rem_digit:
    mov dl,al
    mov ah,02h
    int 21h

mov ax,dx
and ax,0Fh
add ax,30h
cmp ax,39h
jle print_fourth_rem_digit
add ax,7

print_fourth_rem_digit:
    mov dl,al
    mov ah,02h
    int 21h

ret
