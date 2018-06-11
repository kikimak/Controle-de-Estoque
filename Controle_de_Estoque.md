#include <stdio.h> //libera as funçoes de entrada e saida.
#include <stdlib.h>
#include <conio.h>
#include <locale.h>// acentos e caracteres especiais



int main(void){
bool cadEmp;//verificação de cadastro de empresa para nao cadastrar mais de uma vez.
bool cadClient;// verificação de cadastro de cliente para nao cadastrar mais de uma vez.
bool cadProd;//verificação de cadastro do produto para nao cadastrar mais de uma vez.
char nomEmp [100];//nome da empresa
char codEmp [100];//CNPJ DA EMPRESA
char telEmp [100];// telefone da empresa
const int LINHA=10;//quantidade de registros que podem ser armazenados no Produto.
const int LINHAS=15;//quantidade de registros que podem ser armazenados em Cliente.
const int COLUNA=60;
char nomProd[LINHA][COLUNA];//matriz
char precoProd[LINHA][COLUNA];
char quantEstoq[LINHA][COLUNA];
char nomClient[LINHAS][COLUNA];
char telClient[LINHAS][COLUNA];
char cepClient[LINHAS][COLUNA];
int opc; // OPCAO MENU
int l;//nome do produto
int s;//preço produto
int q;//quantidade de produtos cadastrados
int t;//quantidade estoq
int a;//nome do Cliente
int b;//telefone do cliente
int c;//CEP do cliente
int z;//DIGITAR A QUANTIDADE DE CADASTROS
int editProd;//OPC DE EDITAR PRODUTO
int editClient;//OPC DE EDITAR CLIENTE







	
//Vai executar o que ta dentro do 'do' enquanto opc nao entrar nas opçoes do switch
do { 
	
	
	printf ("-----BEM VINDO AO CONTROLE DE PRODUTOS-----\n");
	printf ("1- CADASTRAR EMPRESA \n");
	printf ("2- CADASTRAR PRODUTO \n");
	printf ("3- CADASTRAR CLIENTE \n");
	printf ("4- CONSULTAR PRODUTOS \n");
	printf ("5- CONSULTAR CLIENTE \n");
	printf ("6- ALTERAR PRODUTO \n");
	printf ("7- ALTERAR CLIENTE \n");
	printf ("8- SAIR \n");
	printf ("\n DIGITE A OPCAO DESEJADA:");
	scanf("%d", &opc);
	fflush(stdin);
	system("cls");
	
switch (opc){

		case 2: 
if(opc==2){

		if (cadEmp==true and cadProd==false){//enquanto cadEmp (VERIFICAÇAO CADASTRO DE EMPRESA) empresa nao for cadastrada nao pode cadastrar produto regra de negocio.
			
				printf("Digite a quantidade de produtos para cadastrar (MAX 10): ");
				scanf("%d", &q);
				if (q >= 11){
					printf("MAXIMO 10!!");
					getch();
					system("cls");
					break;
				}
				
				fflush(stdin);
				system("cls");
				

		   		 for(int l=0; l<q; l++)
		    {
		    	printf("CNPJ EMPRESA CADASTRADA: %s \n", codEmp);
		    	printf("TELEFONE : %s \n", telEmp);
		    	printf("----------------------------------------------------\n");
		        printf("Digite o nome do produto %d: ",l,(l+1));
		        gets(nomProd[l]);
		        printf("\n");
		        system("cls");
    
		    }	 
				 for(int s=0; s<q; s++)
		    {	printf("CNPJ EMPRESA CADASTRADA: %s \n", codEmp);
		    	printf("TELEFONE : %s \n", telEmp);
		    	printf("----------------------------------------------------\n");
		        printf("Digite o preco do produto %d:  ",(s+1));
		        gets(precoProd[s]);
		        printf("\n");
		        system("cls");
		    }
	    		 for(int t=0; t<q; t++)
		    {
		    	printf("CNPJ EMPRESA CADASTRADA: %s \n", codEmp);
		    	printf("TELEFONE : %s \n", telEmp);
		    	printf("----------------------------------------------------\n");
		        printf("Digite a quantidade do produto %d em estoque : ",(t+1));
		        gets(quantEstoq[t]);
		        printf("\n");
		        system("cls");
		    }
		    cadProd=true;
		    printf("\nVoltar ao Menu Anterior \n");
			getch();
			system("cls");
			break;
			
		}else {
			printf("EMPRESA NAO CADASTRADA OU PRODUTO JA CADASTRADO!!");
			printf("\nVoltar ao Menu Anterior \n");
			getch();
			system("cls");
			break;

		}
}//fim opc==2
		case 1: 
if(opc==1){

				printf ("------CADASTRO DE EMPRESA------ \n");
				printf ("\n DIGITE O NOME DA EMPRESA: ");
				scanf(" %[^\n]s", &nomEmp);// ^\ n força scanf pegar todo char so finaliza depois do enter
				setbuf(stdin, NULL); //LIMPA O BUFFER
				printf ("\n CNPJ: ");
				scanf("%[^\n]s", &codEmp);
				setbuf(stdin, NULL);
				printf ("\n Telefone: ");
				scanf("%s", &telEmp);
				printf("\nVoltar ao Menu Anterior \n");
				getch();
				system("cls");
				cadEmp=true;
				break;
}//fim opc==1
				
		case 3 :
if(opc==3){

			if(cadClient==false){

				printf("Digite a quantidade de Clientes para cadastrar (MAX 15): ");
				scanf("%d", &z);
				
				if(z >= 16){
					printf("MAXIMO 15!!");
					getch();
					system("cls");
					break;
				}
					system("cls");
					
					
			
				for(int a=0; a<z; a++)
 			   {
 			   	setbuf(stdin, NULL);
		        printf("Digite o nome do Cliente %d: ",a,(a+1));
    		    gets(nomClient[a]);
    		    printf("\n");
    		    system("cls");
    		    
    
   				}	 
				 for(int b=0; b<z; b++)
    			{
    			printf("Digite o telefone do Cliente %d:  ",(b+1));
				gets(telClient[b]);
		        printf("\n");
		        system("cls");
			    }
	    		 for(int c=0; c<z; c++)
			    {
		        printf("Digite o CPF do cliente %d : ",(c+1));
		        gets(cepClient[c]);
		        printf("\n");
		        system("cls");
			    }
				cadClient=true;
				printf("\n Voltar ao Menu Anterior \n");
				getch();
				system("cls");
				break;
						
			}else{
				printf("\n Cliente ja cadastrado!!\n");
				printf("\n Voltar ao Menu Anterior \n");
				getch();
				system("cls");
				break;
			}
	
					
}//fim opc==3
		
		case 4 :
if(opc==4){

			if (cadProd==true){
			printf("PRECO DO PRODUTO:\n");
	    		for(int s=0; s<q; s++)
	   		{
  			    printf("COD:%d  PRECO:%s\n",s, precoProd[s]);
		    }
    
   			printf("NOME DOS PRODUTOS:\n");
    			for(int l=0; l<q; l++)
			{
   			 	printf("COD:%d  NOME:%s\n",l, nomProd[l]);
			}
	
	 		printf("QUANTIDADE DOS PRODUTOS:\n");
    			for(int t=0; t<q; t++)
			{
    			printf("COD:%d  QUANTIDADE:%s\n",t, quantEstoq[t]);
			}

			printf("\n  Voltar ao Menu Anterior: \n");
			getch();
			system("cls");
			fflush(stdin);
			break;
			}else{
				printf("NENHUM PRODUTO CADASTRADO!!\n");
				printf("\n Voltar ao Menu Anterior: \n");
				getch();
				system("cls");
				break;
			}
}//fim opc==4
		case 5 :
			
if(opc==5){

			if (cadClient==true ){
			    printf("NOME DOS CLIENTES CADASTRADOS:\n");
   				 for(int a=0; a<z; a++)
				{
    				printf("COD:%d  NOME: %s\n",a,nomClient[a]);
				}
	
				printf("TELEFONE DOS CLIENTES:\n");
   				 for(int b=0; b<z; b++){
  			  	printf("COD:%d  TEL: %s\n",b,telClient[b]);
				}
				printf("CEP DOS CLIENTES:\n");
			     for(int c=0; c<z; c++){
		    	printf("COD:%d  CEP: %s\n",c, cepClient[c]);
				}
				getch();
				system("cls");
				break;
			
			}else {
				printf("CLIENTE NAO CADASTRADO!!");
				printf("\n  Voltar ao Menu Anterior: \n");
				getch();
				system("cls");
				break;
				
				
			}
		
}//fim opc==5		
	
		case 6:
if(opc==6){

		if(cadProd==true){
		
			printf("<< DIGITE O PRODUTO QUE DESEJA ALTERAR:>>> \n");
			printf("1- NOME: \n");
			printf("2- PRODUTO: \n");
			printf("3- QUANTIDADE: \n");
			printf("O que deseja alterar em produto:\n");
			scanf("%d", &editProd);
			switch(editProd){
				case 2:
						printf("<<Produtos cadastrados>>> \n");
						printf("PRECO DO PRODUTO: \n");
	    					for(int s=0; s<q; s++)
	   					{
  						    printf("COD:%d  PRECO:%s\n",s, precoProd[s]);
					    }
					    printf ("Digite o codigo do produto que deseja alterar: \n");
						scanf("%d", &s);
						if(s<=q){
						
						fflush(stdin);
						system("cls");
						printf("COD: %d preco:%s \n",s, precoProd[s]);
						printf("------------------------------------------ \n ");
						printf("Novo preco para colocar em produto:", (s));
						gets(precoProd[s]);
		      			system("cls");
		      			break;
		      		}else{
		      					system("cls");
								printf ("CODIGO ERRADO!! \n\n");
								break;
					  }
    			case 1:
    					printf("<<Produtos cadastrados>>> \n");
   						printf("NOME DOS PRODUTOS:\n");
    						for(int l=0; l<q; l++)
						{
   					 	printf("COD:%d  NOME:%s\n",l, nomProd[l]);
						}
						printf ("Digite o codigo do produto que deseja alterar: \n");
						scanf("%d", &l);
						if(l<=q){
						
						fflush(stdin);
						system("cls");
						printf("COD: %d QUANTIDADE:%s \n",l, nomProd[l]);
						printf("------------------------------------------ \n ");
						printf("Novo nome para colocar em produto:", (l));
						gets(nomProd[l]);
		      			system("cls");
		      			break;
						}else{
								system("cls");
								printf ("CODIGO ERRADO!! \n\n");
								break;
						}
				case 3:
						printf("<<Produtos cadastrados>>> \n");
	 					printf("QUANTIDADE DOS PRODUTOS:\n");
   				 			for(int t=0; t<q; t++)
						{
    					printf("COD:%d  QUANTIDADE:%s\n",t, quantEstoq[t]);
						}
						printf ("Digite o codigo do produto que deseja alterar: \n");
						scanf("%d", &t);
						if(t<=q){
						
						fflush(stdin);
						system("cls");
						printf("COD: %d QUANTIDADE:%s \n",t, quantEstoq[t]);
						printf("------------------------------------------ \n ");
						printf("Nova quantidade para colocar em produto:", (t));
						gets(quantEstoq[t]);
		      			system("cls");
		      			break;
		      		}else{
		      					system("cls");
								printf ("CODIGO ERRADO!! \n\n");
								break;
					  }
						
				default:
						printf ("NENHUMA OPC DIGITADA!!");
						getch();
						break;
					
			}//FIM SWITCH 2
		}else{
		 printf("PRODUTO NAO CADASTRADO!!");
		 getch();
		 system("cls");
		 break;
		}
		
}//fim opc==6
		case 7:
if(opc==7){
		
			if(cadClient==true){
		
			printf("<< DIGITE OS DADOS QUE DESEJA ALTERAR:>>> \n");
			printf("1- NOME: \n");
			printf("2- TELEFONE: \n");
			printf("3- CEP: \n");
			printf("O que deseja alterar em produto:\n");
			scanf("%d", &editClient);
			switch(editClient){
				case 1:
						printf("<< NOMES CADASTRADOS >>> \n");
						printf("NOME DO CLIENTE: \n");
	    					for(int a=0; a<z; a++)
	   					{
  						    printf("COD:%d  NOME:%s\n",a, nomClient[a]);
					    }
					    printf ("Digite o codigo do nome que deseja alterar: \n");
						scanf("%d", &a);
						fflush(stdin);
						if (a<=z){
						
							system("cls");
							printf("COD: %d NOME:%s \n",a, nomClient[a]);
							printf("------------------------------------------ \n ");
							printf("Novo nome para colocar em cliente:", (a));
							gets(nomClient[a]);
			      			system("cls");
			      			break;
			      		}else{
			      				system("cls");
								printf ("CODIGO ERRADO!! \n\n");
								break;
						  }
						  
						  
    			case 2:
    					printf("<< TELEFONES CADASTRADOS >> \n");
   						printf("TELEFONE DOS CLIENTES:\n");
    						for(int b=0; b<z; b++)
						{
   					 	printf("COD:%d  TEL:%s\n",b, telClient[b]);
						}
						printf ("Digite o telefone do cliente que deseja alterar: \n");
						scanf("%d", &b);
						if(b<=z){
						
						fflush(stdin);
						system("cls");
						printf("COD: %d TELEFONE:%s \n",b, telClient[b]);
						printf("------------------------------------------ \n ");
						printf("Novo telefone para colocar em cliente:", (b));
						gets(telClient[b]);
		      			system("cls");
		      			break;
		      		}else{
		      					system("cls");
								printf ("CODIGO ERRADO!! \n\n");
								getch();
								break;
					  }
				case 3:
						printf("<< CEP DOS CLIENTES >>> \n");
	 					printf("QUANTIDADE DE CEP:\n");
   				 			for(int c=0; c<z; c++)
						{
    					printf("COD:%d  CEP:%s\n",c, cepClient[c]);
						}
						printf ("Digite o codigo do cep do cliente que deseja alterar: \n");
						scanf("%d", &c);
						if(c<=z){
						
						fflush(stdin);
						system("cls");
						printf("COD: %d CEP:%s \n",c, cepClient[c]);
						printf("------------------------------------------ \n ");
						printf("Novo cep para colocar em cliente: ", (c));
						gets(cepClient[c]);
		      			system("cls");
		      			break;
						}else{
								system("cls");
								printf ("CODIGO ERRADO!! \n\n");
								getch();
								break;
					}
				default:
						
						printf ("NENHUMA OPC DIGITADA!!");
						getch();
						system("cls");
						break;
					
			}//FIM SWITCH 2
		}else{
		 printf("CLIENTE NAO CADASTRADO!!");
		 getch();
		 system("cls");
		 break;
		}
}//fim OPC==7
		case 8: 
		if(opc==8){
		
			printf ("VOCE SAIU!!");
			return 1;
		}//fim opc==8
		
		default: 
		if(opc){
				system("cls");
				printf ("NENHUMA OPCAO ACIMA DIGITADA!! \n\n");
				getch();
				system("cls");
				break;
		}
	}// FIM SWITCH
		
}/*FIM DO */while (opc);// enquanto OPC 

}//fim main
