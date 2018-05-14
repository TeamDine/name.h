# name.h
///Cabecera de la clase Name (acepta nombres válidos)
#ifndef NAME_H_INCLUDED
#define NAME_H_INCLUDED

/*** Cabeceras del sistema***/
#include <string>

class Name{
    private:
        std::string last;
        std::string first;

    public:
        Name();             ///Constructor base
        Name(const Name&);  /// Constructor Copia
        Name(const std::string&, std::string&);  ///Constructor Parametrizado

        /*** getters ***/
        std::string getLast();
        std::string getFirst();

        /*** setters ***/
        void setLast(const std::string&);
        void setFirst(const std::string&);

        std::string toString();     ///Imprime nombre
        bool isName(Name& );        ///Checa si es un nombre válido

        /*** Sobrecarga de operadores***/
        Name& operator = (const Name&);
        bool operator == (Name&);
        bool operator != (Name&);
        bool operator < (Name&);
        bool operator <= (Name&);
        bool operator > (Name&);
        bool operator >= (Name&);

        /*** Operadores de escritura/lectura ***/
        friend std::ostream& operator << (std::ostream&, Name&);
        friend std::istream& operator >> (std::istream&, Name&);
};

#endif // NAME_H_INCLUDED

