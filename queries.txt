% gender facts

male(mohammed).
male(saad).
male(abdulelah).
male(fares).
male(khaled).
male(sultan).

female(fatemah).
female(basmah).
female(ghaida).
female(layan).
female(lamees).


% parent facts

parent(fatemah, basmah).
parent(mohammed, basmah).

parent(basmah, abdulelah).
parent(saad, abdulelah).

parent(basmah, fares).
parent(saad, fares).

parent(basmah, ghaida).
parent(saad, ghaida).

parent(basmah, khaled).
parent(saad, khaled).

parent(basmah, layan).
parent(saad, layan).

parent(basmah, lamees).
parent(saad, lamees).

parent(ghaida, sultan).


% rules

father(X, Y) :-
    male(X),
    parent(X, Y).

mother(X, Y) :-
    female(X),
    parent(X, Y).

brother(X, Y) :-
    male(X),
    parent(P, X),
    parent(P, Y),
    X \= Y.

sister(X, Y) :-
    female(X),
    parent(P, X),
    parent(P, Y),
    X \= Y.