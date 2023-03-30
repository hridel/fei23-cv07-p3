# Příklad 3
## Binární soubor (fseek)

Napište program, který:
- načte binární soubor _hdata.bin_ (dostupný na STAGu) obsahující celá čísla
- zjistí počet čísel a vypíše jej na obrazovku
- vypíše 1., 10., 100. a 1000. prvek (v souboru se bude pohybovat pomocí **fseek**)

---

**Nápověda:**

```c
int fseek(__sFILE *, long offset, int whence)
long ftell(__sFILE *)
```


Funkce fseek() slouží k přesunu pozice v souboru. Její syntaxe je následující:

`int fseek(FILE *stream, long int offset, int whence);`

Parametry funkce jsou:
- **stream** - ukazatel na souborovou proměnnou typu `FILE`
- **offset** - počet bajtů, o které se má posunout pozice
- **whence** - určuje, odkud se má počítat nová pozice

Parametr whence může nabývat těchto hodnot:
- `SEEK_SET` - počítá se od začátku souboru
- `SEEK_CUR` - počítá se od aktuální pozice
- `SEEK_END` - počítá se od konce souboru

Například volání funkce `fseek(f, 9L * sizeof(int), SEEK_SET)` posune pozici v souboru na 10. prvek.