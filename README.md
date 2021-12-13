# CybersecurityUnipd
Corso di Cybersecurity presso l'universita di Padova
 --------------------------------------------------------------GDB
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
 x/s (char *) flag_buf                  /stampa una variabile come stringa
 disassemble bash                       /mostra assembly della funzione
 c                                      /contiuna dopo br
 
 --------------------------------------------------------------Comandi utili
 strings                                /mostra funzioni
 file nome                              /mostra (Ex:intel 80386) che indica anche l architettura del programma
 checksec info                          /
 pwn checksec                           /stessa cosa con checksec
 ----------->Checksec's outputs
 1- RELRO                               /Relocation Read-Only la tabella GOT non puo essere editata. Vedi es 1_GOT (exit call overlapped)
 2- CANARY                              /Controllo sul return della funzione chiamata che si accerta che riporti alla funzione precedente
 3- NX                                  /Non-Executable La stack non è eseguibile
 4- PIE                                 /Position Independent Executable Indirizzi shiftati di uno stesso offset comune
 Fonti: https://blog.siphos.be/2011/07/high-level-explanation-on-some-binary-executable-security/ e @Stecca
 --------------------------------------------------------------Info utili
 puntatore in 32bit e grande 4bit
 puntatore in 64bit e grande 8bit
 
 --------------------------------------------------------------Radare
 r2 file
 aaaa inizializza
 afl  mostra indirizzi funzioni
 pd 1 @ (nome funzione ottenuto con afl) /stampa indirizzo comando
 s main salta al main
 pdf @ main mostra il main disassemblato
 pdc mostra la funzione in cui sei decompilata con radare
 pdg mostra la funzione in cui sei decompilata con ghidra SERVE rdghidra
 v entra in modalità visual
 
 --------------------------------------------------------------Pwn tools
 pwn pytohn
 asm(shellcraft.sh())                    /crea una shell 
 
 --------------------------------------------------------------Ghidra
 
 --------------------------------------------------------------Ida
  Hex 90 = nop
