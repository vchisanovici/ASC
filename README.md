# ASC
.data 
	Print=4
	Close=10
	mesaj1: .asciiz "Scrieti x0: "
	mesaj2: .asciiz "Scrieti x1: "
	mesaj3: .asciiz "Scrieti n: "
	mesaj4: .asciiz "Sirul este: "
.text

afisare:

	add $a0,$a1,$zero
	li $v0,1
	syscall
	
	add $a0,$zero,32
	li $v0,11
	syscall
	
	add $a0,$a2,$zero
	li $v0,1
	syscall
	
	j $ra
.end afisare


main:
	la $a0,mesaj1						#afisare mesaj1
	li $v0,4
	syscall
	
	li $v0,5							#citire x0
	syscall
	
	add $a1,$zero,$v0					#salvare x0
	
	la $a0,mesaj2						#afisare mesaj2
	li $v0,4
	syscall
	
	li $v0,5							#citire x1
	syscall
	
	add $a2,$zero,$v0					#salvare x1
	
	la $a0,mesaj3
	li $v0,4
	syscall
	
	li $v0,5							#citire n
	syscall
	
	add $a3,$zero,$v0					#salvare n
	
	la $a0,mesaj4
	li $v0,4
	syscall
	
	jal afisare
	
	li $v0,10
	syscall
.end main

