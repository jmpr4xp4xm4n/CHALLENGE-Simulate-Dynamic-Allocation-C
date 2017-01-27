#include <stdio.h>
#include <ctype.h>

struct node {
    char c;
    struct node *next;
};

void output(struct node *l, FILE * fp, char t)
{
    if (!l)
    return;
    output(l->next, fp, t);
    fputc(l->c == t ? '*' : l->c, fp);
}

void read_one(struct node *l, FILE * in, FILE * out, char t)
{
    int r, c = fgetc(in);
    struct node n = { c, l };
    if (c == EOF) {
    output(l, out, t);
    fputc('\n', out);
    return;
    }
    if (!isblank(c))
    t = c;
    read_one(&n, in, out, t);
}

int main(void)
{
    read_one(0, stdin, stdout, 0);
    return 0;
}
