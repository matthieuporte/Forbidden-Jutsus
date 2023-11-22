
[Motorola 68000 Doc](http://www.easy68k.com/files/EASy68KQuickRef.pdf)
[Debug.pro/assembly](http://www.debug-pro.com/epita/archi/s3/en/)

### Geany Shortcuts

**\[f8\]** assemble 
**\[f5\]** run the program
**\[f11\]** execute one instruction
**\[f10]** execute one line _(doesn’t go in functions)_
**\[back space\]** go back one instruction
**\[f9\]** run the whole thing
**\[ctrl+R\]** reset the 68000
**\[F4\]** run the video output

### Motorola 68000

Startup code using Video output

```asm6502
					; ==============================
					; Definitions of Constants
					; ==============================
					; Video Memory
					; ------------------------------
					
VIDEO_START 		equ $ffb500 						; Starting address
VIDEO_WIDTH 		equ	480 							; Width in pixels
VIDEO_HEIGHT 		equ 320 							; Height in pixels
VIDEO_SIZE 			equ (VIDEO_WIDTH*VIDEO_HEIGHT/8) 	; Size in bytes
BYTE_PER_LINE 		equ (VIDEO_WIDTH/8) 				; Number of bytes per line

					; ==============================
					; Vector Initialization
					; ==============================
					
					org $0
					
vector_000 			dc.l VIDEO_START 					; Initial value of A7
vector_001 			dc.l Main 							; Initial value of the PC

					; ==============================
					; Main Program
					; ==============================

					org $500
					
Main 				; Tests

					illegal
					
					; ==============================
					; Subroutines
					; ==============================

					
					; ==============================
					; Data
					; ==============================

```
