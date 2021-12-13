
## GDB
     gdb nomefile                       /per aprire il file
     run                                /per runnare il programma
     bt                                 /backtrace mostra le chiamate fatte finora dal programma
     br *0xBD o br main                 /mette breakpoint su l indirizzo HEX passato
     jump printflag                     /salta alla funzione richiesta need br and run
     clear main                         /toglie i brakpoint dalla funzione indicata
     info registers                     /mostra i registri
     info variables                     /mostra variabili
     printf "%s", (char *) flag_buf 
     oppure 
     x/s (char *) flag_buf              /stampa una variabile come stringa
     disassemble bash                   /mostra assembly della funzione
     c                                  /contiuna dopo br
## Comandi utili
     strings                            /mostra funzioni
     file nome                          /mostra (Ex:intel 80386) l'architettura del programma
     checksec info studia
     pwn checksec                       /stessa cosa con checksec
## Info utili

     puntatore in 32bit è grande 4bit
     puntatore in 64bit è grande 8bit

 
## Radare
     r2 file                            /apre file
     aaaa                               /inizializza
     afl                                /mostra indirizzi funzioni
     pd 1 @ (funzione)                  /stampa indirizzo comando
     s main                             /salta al main
     pdf @ main                         /mostra il main disassemblato
     pdc                                /mostra la funzione in cui sei decompilata con radare
     pdg                                /mostra la funzione in cui sei decompilata con ghidra SERVE rdghidra
     v                                  /entra in modalità visual
## Pwn tools

     pwn Python
     asm(shellcraft.sh())               /crea una shell 

 
## Ghidra
 
## Ida

      Hex 90 = nop
