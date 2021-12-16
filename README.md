# Cybersecurity Tools
### Toolkit di supporto per il corso di Cybersecurity presso l'Università degli Studi Padova


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
     x/200bx $esp                       /mostra la stack, se non c'è esp usa rsp
     r < a                              /da come input il file a (da usare con cyclic)
     
## Comandi utili
     strings                            /mostra funzioni
     file nome                          /mostra architettura (Ex:intel 80386) 
     pwn cyclic 100 > a                 /crea un pattern lungo 100 dentro al file a
     
     
### Checksec
     pwn checksec nomefile              /simile a comando file ma da piu dettagli sull' eseguibile
     -Outputs di Checksec
      1- RELRO                          /Relocation Read-Only la tabella GOT non puo essere editata. Vedi es 1_GOT (exit call overlapped)
      2- CANARY                         /Controllo sul return della funzione chiamata che si accerta che riporti alla funzione precedente
      3- NX                             /Non-Executable La stack non è eseguibile
      4- PIE                            /Position Independent Executable Indirizzi shiftati di uno stesso offset comune
     Fonti: https://blog.siphos.be/2011/07/high-level-explanation-on-some-binary-executable-security/ e @Stecca
 
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

## Pwntools
     from pwn import *                  /importa pwntools in uno script
     p.sendline(_msg_)                  /scrive una stringa nel terminale
     p.sendlineafter('_str_', _msg_)    /scrive una stringa nel terminale solo dopo aver letto una certa stringa
     p.recvall()                        /salva le stampe del terminale (da assegnare ad una variabile oppure printare)
     p.interactive()                    /permette di interagire con il terminale
     asm(shellcraft.sh())               /crea una shell 
     offset = cyclic_find("kaaa")       /ritorna la distanza della stringa kaaa sul cyclic
     
## Ida

     90 = nop                           /90 in esadecimale corrisponde a un istruzione assembly nulla: nop
 
## Ghidra
     
## Info utili

     puntatore in 32bit è grande 4bit
     puntatore in 64bit è grande 8bit
