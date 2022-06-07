# RESOLUÇÕES EXERCÍCIOS PLATAFORMA BEECROWD - C++
[Perfil Beecrowd](https://www.beecrowd.com.br/judge/pt/profile/424268)

## 1047 Tempo de Jogo com Minutos
``#include <iostream>
using namespace std;
int main(){
			int hi, hf, mi, mf, hj, mj;
			cin>>hi>>mi>>hf>>mf;
			if (hi==hf)
			{
				if (mi<mf)/*casos onde jogo possui menos de 60min*/
				{
					hj=0; mj=mf-mi;
					cout<<"O JOGO DUROU "<<hj<<" HORA(S) E "<<mj<<" MINUTO(S)"<<'\n';
				}
				else
				{
					if (mi==mf)/*caso com 24h*/
					{
						hj=24; mj=0;
						cout<<"O JOGO DUROU "<<hj<<" HORA(S) E "<<mj<<" MINUTO(S)"<<'\n';
					}
					else /*caso com mais de 23h*/
					{
						hj=23;
						mj=(60-mi)+mf;
						cout<<"O JOGO DUROU "<<hj<<" HORA(S) E "<<mj<<" MINUTO(S)"<<'\n';
					}
				}	
			}
			else
			{
				if (hi<hf)/*caso onde jogo não passe da meia noite*/
				{
					hj=hf-hi;
					if (mi<=mf)/*caso para horas cheias*/
					{
						mj=mf-mi;
						cout<<"O JOGO DUROU "<<hj<<" HORA(S) E "<<mj<<" MINUTO(S)"<<'\n';
					}
					else
					{
						hj=hj-1;
						mj=(60-mi)+mf;
						cout<<"O JOGO DUROU "<<hj<<" HORA(S) E "<<mj<<" MINUTO(S)"<<'\n';
					}	
				}
				else /*caso onde jogo passe da meia noite (hi>hf)*/
				{
					hj=(24-hi)+hf;
					if (mi<=mf)/*caso para horas cheias*/
					{
						mj=mf-mi;
						cout<<"O JOGO DUROU "<<hj<<" HORA(S) E "<<mj<<" MINUTO(S)"<<'\n';
					}
					else
					{
						hj=hj-1;
						mj=(60-mi)+mf;
						cout<<"O JOGO DUROU "<<hj<<" HORA(S) E "<<mj<<" MINUTO(S)"<<'\n';
					}
				}
			}
}``

## 1099 Soma de Ímpares Consecutivos II
``#include <iostream>
using namespace std;
int main (){
			int N, n, X, Y, Z, s;
			cin>>N;
			int soma[N];
			for (n=0; n<N; n++)
			{
				soma[n]=0;
				cin>>X>>Y;
				if (Y<X)
				{
					for (Z=Y+1; Z<X; Z++)
					{
						if (Z%2==1)
						{
							soma[n]=soma[n]+Z;
						}
					}
				}
				else
				{
					for (Z=X+1; Z<Y; Z++)
					{
						if (Z%2==1)
						{
							soma[n]=soma[n]+Z;
						}
					}
				}
				
			}
			for (s=0; s<N; s++)
			{
				cout<<soma[s]<<"\n";
			}
}``

## 1115 Quadrante
``#include <iostream>
using namespace std;
int main (){
			int x, y;
			cin>>x>>y;
				while (x&&y!=0){
					if (x>0){
						if (y>0){
							cout<<"primeiro"<<'\n';}
						else{
							cout<<"quarto"<<'\n';}}
					else{
						if (y>0){
							cout<<"segundo"<<'\n';}
						else{
							cout<<"terceiro"<<'\n';}}
					cin>>x>>y;}}``

## 1131 - Grenais
``#include <iostream>
using namespace std;
int main (){
			int INT, GRE, GOLINT, GOLGRE, i, x, VINT, VGRE, EMP;
			i=0; GOLINT=0; GOLGRE=0, EMP=0, VINT=0, VGRE=0;
			cin>>INT>>GRE;
			i=i+1;
			GOLINT=GOLINT+INT;
			GOLGRE=GOLGRE+GRE;
			/*SOMA DAS VITORIAS*/
			if (INT>GRE)
			{
				VINT=VINT+1;
			}
			else
			{
				if (INT<GRE)
				{
					VGRE=VGRE+1;
				}
				else
				{
					EMP=EMP+1;
				}
			}
			/*NOVA SEQUENCIA DE DADOS*/
			cout<<"Novo grenal (1-sim 2-nao)"<<'\n';
			cin>>x;
			/*repetição*/
			while (x==1)
			{
				cin>>INT>>GRE;
				i=i+1;
				GOLINT=GOLINT+INT;
				GOLGRE=GOLGRE+GRE;
				if (INT>GRE)
				{
					VINT=VINT+1;
				}
				else
				{
					if (INT<GRE)
					{
						VGRE=VGRE+1;
					}
					else
					{
						EMP=EMP+1;
					}
				}
				/*NOVA SEQUENCIA DE DADOS*/
				cout<<"Novo grenal (1-sim 2-nao)"<<'\n';
				cin>>x;
			}
			if (x==2)
			{
				cout<<i<<" grenais"<<'\n';
				cout<<"Inter:"<<VINT<<'\n';
				cout<<"Gremio:"<<VGRE<<'\n';
				cout<<"Empates:"<<EMP<<'\n';
				if (VINT>VGRE)
				{
					cout<<"Inter venceu mais"<<'\n';
				}
				else
				{
					if (VINT<VGRE)
					{
						cout<<"Gremio venceu mais"<<'\n';
					}
					else
					{
						if (VINT==VGRE)
						{
							cout<<"Nao houve vencedor"<<'\n';
						}
					}
				}
			}
}``

## 1132 Múltiplos de 13
``#include <iostream>
using namespace std;
int main (){
			int soma, X, Y, i;
			soma=0;
			cin>>X>>Y;
			if (Y>X)
			{
				for (i=X; i<=Y; i++)
				{
					if (i%13!=0)
					{
						soma=soma+i;
					}
				}
				cout<<soma<<'\n';
			}
			else
			{
				if (X>Y)
				{
					for (i=Y; i<=X; i++)
					{
						if (i%13!=0)
						{
							soma=soma+i;
						}
					}	
				}
				cout<<soma<<'\n';
			}
}``

## 1134 Tipo de Combustível
``#include <iostream>
using namespace std;
int main (){
			int A, G, D, Comb;
			Comb=0;
			A=0;
			G=0;
			D=0;
			while (Comb!=4)
			{
				cin>>Comb;
				if (Comb>0&&Comb<=4)
				{
					if (Comb==1)
					{
						A=A+1;
					}
					else
					{
						if (Comb==2)
						{
							G=G+1;
						}
						else
						{
							if (Comb==3)
							{
								D=D+1;
							}
						}
					}
				}
			}
			cout<<"MUITO OBRIGADO"<<'\n';
			cout<<"Alcool: "<<A<<'\n';
			cout<<"Gasolina: "<<G<<'\n';
			cout<<"Diesel: "<<D<<'\n';
}``

## 1145 Sequência Lógica 2
``#include <iostream>
using namespace std;
int main (){
			int x, y, i, j;
			cin>>x>>y;
			if (1<x<20 && x<y<100000)
			{
				for (i=1, j=0; i<=y; i++)
				{
					cout<<i;
					j++;
					/*CONDIÇÃO PARA Q IMPRIMA ESPAÇO APOS CADA NUMERO EXCETO O ULTIMO DA LINHA*/
					if (j<x)
					{
						cout<<" ";
					}
					else
					{
						cout<<'\n';
						j=0;
					}
				}
			}
}``

## 1146 Sequências Crescentes
``#include <iostream>
using namespace std;
int main (){
			int x, i;
			cin>>x;
			while (x!=0)
			{
				for (i=1; i<=x; i++)
				{
					cout<<i;
					if (i<x)
					{
						cout<<" ";
					}
					else
					{
						cout<<'\n';
					}
				}
				cin>>x;
			}
}``

## 1149 Somando Inteiros Consecutivos
``#include <iostream>
using namespace std;
int main (){
			int A, N, i, soma;
			soma=0;
			cin>>A>>N;
			if (N<=0)
			{
				while (N<=0)
				{
					cin>>N;
				}
			}
			for (i=0; i<=N-1; i++)
			{
				soma=soma+(A+i);
			}
			cout<<soma<<'\n';
}``

## 1150 Ultrapassando Z
``#include <iostream>
using namespace std;
int main (){
			int x, z, i, j, soma;
			cin>>x>>z;
			soma=x; j=0;
			if (z<=x)
			{
				while (z<=x)
				{
					cin>>z;
				}
			}
			for (i=x; soma<=z+1; i++)
			{
				soma=soma+i;
				j++;
			}
			cout<<j<<'\n';
}``

## 1151 Fibonacci Fácil
``#include <iostream>
using namespace std;
int main (){
			int x, i, soma, p;
			cin>>x;
			int v[x];
			soma=0;
			if (0<x<46)
			{
				for (i=0; i<x; i++)
				{
					if (i<=1)
					{
						v[i]=i;
						cout<<i<<" ";
					}
					else
					{
						if (i<x-1)
						{
							v[i]=v[i-2]+v[i-1];
							cout<<v[i]<<" ";
						}
						else
						{
							v[i]=v[i-2]+v[i-1];
							cout<<v[i]<<'\n';
						}
					}
				}
			}
}``

## 1153 Fatorial Simples
``#include <iostream>
using namespace std;
int main (){
			int i, n, fatorial;
			cin>>n;
			fatorial=1;
			if (0<n<13)
			{
				for (i=n; i>=1; i--)
				{
					fatorial=fatorial*i;
				}
				cout<<fatorial<<'\n';
			}
}``

## 1154 Idades
``#include <iostream>
#include <iomanip>
using namespace std;
int main (){
			float soma, media;
			int i, x;
			cin>>x; i=0;
			while (x>=0)
			{
				i++;
				soma=soma+x;
				cin>>x;
			}
			media=(soma/i);
			cout<<fixed<<setprecision(2);
			cout<<media<<'\n';
}``

## 1155 Sequência S
``#include <iostream>
#include <iomanip>
using namespace std;
int main (){
			float S, i;
			S=0;
			for (i=1; i<=100; i++)
			{
				S=S+(1/i);
			}
			cout<<fixed<<setprecision(2);
			cout<<S<<'\n';
}``

## 1156 Sequência S II
``#include <iostream>
#include <iomanip>
using namespace std;
int main (){
			double S, i, j;
			S=0;
			for (i=1, j=1; i<=39; i=i+2, j=j*2)
			{
				S=S+(i/j);
			}
			cout<<fixed<<setprecision(2);
			cout<<S<<'\n';
}``

## 1157 Divisores I
``#include <iostream>
using namespace std;
int main (){
			int n, i;
			cin>>n;
			for (i=1; i<=n; i++)
			{
				if (n%i==0)
				{
					cout<<i<<'\n';
				}
			}
}``



