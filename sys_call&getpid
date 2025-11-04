myppidtest.c: 

#include <stdio.h>
#include <lib.h> // For _syscall
#include <unistd.h> // For getpid()

int main(void) {
    int myPid = getpid(); // Pobierz PID bieżącego procesu
    int ret;              // Wynik wywołania systemowego
    message m;            // Struktura wiadomości dla system call

    m.m1_i1 = myPid;      // Ustaw PID w strukturze wiadomości

    // Wywołanie systemowe
    ret = _syscall(MM, GETPPIDFD, &m);

    // Sprawdzenie wyniku
    if (ret < 0) {
        printf("Error: Could not get parent descriptor\n");
    } else {
        printf("Parent process descriptor PID: %d\n", ret);
    }

    return 0; // Zakończ program z sukcesem
}
