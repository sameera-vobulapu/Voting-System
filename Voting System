#include<stdio.h>
#include<string.h>
#include<stdlib.h>
char name[100][100];
char name1[100][100];
char pass[100][100];
char cname[100];
int id[100];
int vote_cand[100]={0};
int n,n1,count[100]={0};
void add_candidates()
{
    printf("enter no of candidates:\n");
    scanf("%d",&n);
    for(int i=1;i<=n;i++)
    {
        printf("enter name of candidate %d:\n",i);
        scanf("%s",name[i]);
    }

}
void view_candidates()
{
 for(int i=1;i<=n;i++)
 {
    printf("candidates are:%s\n",name[i]);
 }
}
void register_voters()
{
    printf("enter no of voters:\n");
    scanf("%d",&n1);
    for(int i=1;i<=n1;i++)
    {
        printf("enter voter %d name:\n",i);
        scanf("%s",name1[i]);
        printf("enter id:\n");
        scanf("%d",&id[i]);
        printf("enter password\n");
        scanf("%s",pass[i]);
    }
}
void view_voters()
{
    for(int i=1;i<=n1;i++)
 {
    printf("voter %d details are:\n",i);
    printf("voter name:%s\n",name1[i]);
    printf("voter id:%d\n",id[i]);
    printf("password:%s\n",pass[i]);
    
 }
}
 int verify_voter()
 {
     int uid;
     char upass[100];  
     printf("enter id:\n");
     scanf("%d",&uid);
     printf("enter pass:\n");
     scanf("%s",upass);
     for(int i=1;i<=n1;i++)
     {
     if(uid==id[i]&&strcmp(upass,pass[i])==0&&count[i]==0)
     {
         return 1;
     }
     }
     printf("invalid details or already voted\n");
     return 0;
 }
 void cast_vote()
 {
     printf("cast your vote for the candidates:\n");
     for(int i=1;i<=n;i++)
     {
     printf("%s\n",name[i]);
     }
     printf("enter cand name:\n");
     scanf("%s",cname);
     
     for(int i=1;i<=n;i++)
     {
     if(strcmp(cname,name[i])==0)
     {
         vote_cand[i]+=1;
         count[i]++;
         printf("ur vote is casted succesfully\n");
     }
     }
 }
 void display_votes()
 {
    printf("\nVotes Count:\n");
    int max_votes = 0, winner_index = 0;

    for(int i = 1; i<=n; i++) 
    {
        printf("%s received %d votes\n", name[i], vote_cand[i]);
        if(vote_cand[i] > max_votes) 
        {
            max_votes = vote_cand[i];
            winner_index = i;
        }
    }
    printf("\nWinner: %s with %d votes!\n", name[winner_index], max_votes);
}
int main()
{
    int choice,c1,c2;
    while(1)
    {
    printf("-------menu-------\n");
    printf("1.manage candidates\n2.manage voters\n3.start voting\n4.display results\n5.Exit\n");
    printf("enter your choice:\n");
    scanf("%d",&choice);
    switch(choice)
    {
        case 1:
        printf("1.add candidates\n2.view candidates\n");
        printf("enter choice:\n");
        scanf("%d",&c1);
        if(c1==1)
        {
            add_candidates();
        }
        else if(c1==2)
        {
            view_candidates();
        }
        else{
            printf("invalid choice\n");
        }
        break;
        case 2:
        printf("1.register voters\n2.view voters\n");
        printf("enter choice:\n");
        scanf("%d",&c2);
        if(c2==1)
        {
            register_voters();
        }
        else if(c2==2)
        {
            view_voters();
        }
        else{
            printf("invalid choice\n");
        }
        break;
        case 3:
        int verified = verify_voter();
        if (verified == 1) 
        {
         cast_vote();
        }
        break;
        case 4:
        display_votes();
        break;
        case 5:
        exit(0);
        break;
        default:
        printf("invalid choice\n");
    }
    }
return 0;
}
