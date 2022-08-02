# td_git_tawqeermunsoo
#include <stdio.h>
	#include <time.h>
	#include <math.h>
	#include <stdlib.h>
	

	int choix_joueur, valeur_a_trouver1, valeur_a_trouver2, r, ess, num_joueur, num_tour,j, score_joueur1, score_joueur2;
	//Fonction pour générer un nombre aléatoire entre 0 et 100
	void plus_moins(int r)
	{
	  srand(time(NULL));
	  valeur_a_trouver1 = rand() % r;
	  valeur_a_trouver2 = rand() % r;
	  //On utilise le do-while loop tant que l'utilisateur essaye de deviner la bonne valeur.
	   do{
	      
	      printf ("|--------------Tour %d--------------|\n",num_tour);
	      printf("Vous etes joueur 1 ou 2? Entrez 1 pour joueur1 et 2 pour joueur2: ");
	      scanf("%d", &num_joueur);
	      printf ("Bonjour joueur %d, c'est votre tour.\n", num_joueur);
	      printf("Le second joueur doit entrer le nombre d'essaie pour vous: ");
	      scanf ("%d",&ess);
	      printf ("Deviner la bonne valeur: "); 
	      if (num_joueur == 1)
	      {
	      for (int i = ess ; i > 0; i--)
	      {
	        
	        scanf("%d", &choix_joueur);
	        //Quand l'utilisateur choisi une valeur moins que la bonne valeur
	        if (choix_joueur < valeur_a_trouver1)
	        {
	          printf("La bonne valeur est plus!\n");
	          printf("Veuillez choisir de nouveau une valeur: ");
	          ess--;
	        }
	  
	      //Quand l'utilisateur choisi une valeur plus grande que la bonne valeur  
	        else if (choix_joueur > valeur_a_trouver1)
	        { 
	          printf("La bonne valeur est moins!\n");
	          printf("Veuillez choisir de nouveau une valeur: ");
	          ess--;
	        }
	        //Quand l'utilisateur a choisi la bonne valeur
	        else 
	        {
	          printf ("Bingo!\nVous avez eu la bonne valeur joueur %d!\n", num_joueur);
	          num_tour--;
	          score_joueur1=ess;
	          break;
	        }
	          
	        //Si nombre d'essaies est au Maximum.
	        if (ess == 0)
	        {
	          printf("Maximum nombre d'essaies. Vous avez perdu.");
	          num_tour--;
	          break;
	        }
	      }
	      }
	      else if (num_joueur == 2)
	      {
	      for (int i = ess ; i > 0; i--)
	      {
	        
	        scanf("%d", &choix_joueur);
	        //Quand l'utilisateur choisi une valeur moins que la bonne valeur
	        if (choix_joueur < valeur_a_trouver2)
	        {
	          printf("La bonne valeur est plus!\n");
	          printf("Veuillez choisir de nouveau une valeur: ");
	          ess--;
	        }
	  
	      //Quand l'utilisateur choisi une valeur plus grande que la bonne valeur  
	        else if (choix_joueur > valeur_a_trouver2)
	        { 
	          printf("La bonne valeur est moins!\n");
	          printf("Veuillez choisir de nouveau une valeur: ");
	          ess--;
	        }
	        //Quand l'utilisateur a choisi la bonne valeur
	        else 
	        {
	          printf ("Bingo!\nVous avez eu la bonne valeur joueur %d!\n", num_joueur);
	          num_tour--;
	          score_joueur2=ess;
	          break;
	        }
	          
	        //Si nombre d'essaies est au Maximum.
	        if (ess == 0)
	        {
	          printf("Maximum nombre d'essaies. Vous avez perdu.");
	          num_tour--;
	          break;
	        }
	      }
	      }
	    
	    }while(num_tour != 0);
	    //Afficher les scores des deux joueurs et le gagnant.
	    printf("::::::::::::::::::Scores:::::::::::::::::::::::\njoueur1--->%d\tjoueur2--->%d\n",score_joueur1,score_joueur2);
	    if (score_joueur1 > score_joueur2)
	    {
	      printf("Bravo! Le gagnant est joueur 1!\n");
	    }
	    else
	      printf("Bravo! Le gagnant est joueur 2!\n");
	}
	    
	

	int main()
	{
	  int r = 100;
	  printf ("Bienvenue au jeu plus ou moins!\n");
	  //Pour choisir le nombre de tour.
	  printf ("Veillez entrez le nombre de tour que vous souhaitez jouer: ");
	  scanf ("%d", &num_tour);
	  //For loop tant que le nombre de tour n'est pas 0.
	  //A chaque tour, le joueur qui doit jouer devra entrer son numero(1 ou 2).
	  for (int j = 1; j= num_tour; j++)
	  { 
	    //Appel de la fonction plus_moins
	    plus_moins(r);
	    return 0;
	  }
	}

