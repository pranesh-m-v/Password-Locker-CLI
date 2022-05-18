#include<stdio.h>
#include<string.h>
#include<stdlib.h>



//declaration of functions

void saveApplicationName(char application[]);
void savePassword(char password[]);
int checkPassword(char password[], int index);
void addPassword();
void editPassword();
void viewAllSavedPasswords();
void deletePassword();
void deleteAllSavedPasswords();
void viewLastPassword();
void contents();



//globally accessable arrays
char passwordArray[50][50] = {"12345678", "87654321", "abcdefgh", "aabbccdd", "AaBbCcDd"};
char applicationArray[50][50] = {"gmail", "facebook", "instagram", "twitter", "netflix"};


//saves the application name in the applicationArray
void saveApplicationName(char application[])
{
    int count = 0;
    while(strlen(applicationArray[count]))
    {
        count++;
    }
    for(int i = 0; i< strlen(application); i++)
    {
        applicationArray[count][i] = application[i];
    }
    //puts(applicationArray[count]);
}


//saves password in passwordArray
void savePassword(char password[])
{
    int count = 0;
    while(strlen(passwordArray[count]))
    {
        count++;
    }
    for(int i = 0; i < strlen(password); i++)
    {
        passwordArray[count][i] = password[i]+i;
    }
    //puts(passwordArray[count]);
}


//it checks whether the given password is valid or not
int checkPassword(char password[], int index)
{
    int count;
    for(int i = 0; i< strlen(password); i++)
    {
        if(password[i] != passwordArray[index][i]-i)
        {
            count++;
        }
            
    }
    if(count == 0)
    {
        return 1;
    }
    else
    {
        return 0;
    }
}


//this function adds the password and applicationName to the array
void addPassword()
{
    char applicationName[32];
    char password[32];
    char y;
    
    //inputs from the user
    printf("Enter application name : ");
    scanf("%s", applicationName);
    printf("Enter Password : ");
    scanf("%s", password);
    printf("Save?       type y to save! or type n to discard\n");
    scanf("%s", &y);
    
    if(y == 'y' || y == 'Y')
    {
        //function call - this saves the input data in the array
        saveApplicationName(applicationName);
        savePassword(password);
    }
        
    printf("your password has been saved successfully\n");
    int c;
    printf("to go back to contents press 5\n");
    five:
    scanf("%d", &c);
    if(c == 5)
    {
        contents();
    }
    else
    {
        printf("enter 5\n");
        goto five;
    }
}


//this function is used to edit the password in the array
void editPassword()
{
    int i = 0, c = 0;
    char newPassword[32];
    
    //empty array
    if(strlen(passwordArray[0])==0)
    {
        printf("empty! no passwords have been added\n");
    }
    
    //if array is not empty the following code executes
    else
    {
        while(strlen(passwordArray[i]))
        {
            printf(" %d   %s : ", i+1, applicationArray[i]);
            puts(passwordArray[i++]);
        }
    }
    printf("type the index value of the Password that needs to be edited\n");
    scanf("%d", &i);
    printf("\nenter new password : ");
    scanf("%s", newPassword);
    strcpy(passwordArray[i-1], newPassword);
    printf("to go back to contents press 5\n");
    five:
    scanf("%d", &c);
    if(c == 5)
    {
        contents();
    }
    else
    {
        printf("enter 5\n");
        goto five;
    }
}


//this function deletes only the password but not the applicationName
void delPassword()
{
    int i = 0, c = 0;
    char newPassword[32];
    
    //empty array
    if(strlen(passwordArray[0])==0)
    {
        printf("empty! no passwords have been added\n");
    }
    
    //if array is not empty the following code executes
    else
    {
        while(strlen(passwordArray[i]))
        {
            printf(" %d   %s : ", i+1, applicationArray[i]);
            puts(passwordArray[i++]);
        }
    }
    printf("type the index value of the Password that needs to be deleted\n");
    scanf("%d", &i);
    strcpy(passwordArray[i-1], " ");
    printf("to go back to contents press 5\n");
    five:
    scanf("%d", &c);
    if(c == 5)
    {
        contents();
    }
    else
    {
        printf("enter 5\n");
        goto five;
    }
}


//this functions displays all passwords in the passwordArray
void viewAllSavedPasswords()
{
    int i = 0, c = 0;
    if(strlen(passwordArray[0])==0)
    {
        printf("empty! no passwords have been added\n");
    }
    else
    {
        while(strlen(passwordArray[i]))
        {
            printf(" %d   %s : ", i+1, applicationArray[i]);
            puts(passwordArray[i++]);
        }
    }
    
    printf("to go back to contents press 5\n");
    five:
    scanf("%d", &c);
    if(c == 5)
    {
        contents();
    }
    else
    {
        printf("enter 5\n");
        goto five;
    }
}



//this function deletes the password and applicationName by queue mechanism
void deletePassword()
{
    int ind = 0;
    char password[32], y;
    int i = 0;
    while(strlen(passwordArray[i]))
    {
        printf("%s : ", applicationArray[i]);
        puts(passwordArray[i++]);
    }
    printf("to delete type y\n");
    scanf("%s", &y);
    i = 0;
    if(y == 'y' || y == 'Y')
    {
        int count = 0;
        while(strlen(passwordArray[count]))
        {
            count++;
        }
        for(i = ind; i < count; i++)
        {
            strcpy(passwordArray[i], passwordArray[i+1]);
            strcpy(applicationArray[i], applicationArray[i+1]);
        }
        printf("deletion success!");
    }
    
    printf("to go back to contents press 5\n");
    int c = 0;
    five:
    scanf("%d", &c);
    if(c == 5)
    {
        contents();
    }
    else
    {
        printf("enter 5\n");
        goto five;
    }
}



//this function deletes all the saved Passwords in the array 
void deleteAllSavedPasswords()
{
    int i=0;
    while(strlen(passwordArray[i]))
    {
        strcpy(applicationArray[i], "");
        strcpy(passwordArray[i++], "");
    }
    
    printf("Deleted All Saved Passwords!\n");
    
    printf("to go back to contents press 5\n");
    int c = 0;
    five:
    scanf("%d", &c);
    if(c == 5)
    {
        contents();
    }
    else
    {
        printf("enter 5\n");
        goto five;
    }
}


//this function displays last password
void viewLastPassword()
{
    int count = 0;
    while(strlen(passwordArray[count]))
    {
        count++;
    }
    printf("%s : ", applicationArray[count-1]);
    puts(passwordArray[count-1]);
    
    printf("to go back to contents press 5\n");
    int c = 0;
    five:
    scanf("%d", &c);
    if(c == 5)
    {
        contents();
    }
    else
    {
        printf("enter 5\n");
        goto five;
    }
}



int main()
{
    char y;
    char username[32];
    char password[32];
    
    printf("Enter username : ");
    scanf("%s", username);
    printf("Enter password : ");
    scanf("%s", password);
    
    if(strcmp(username, "user") && strcmp(password, "password"))
    {
        printf("wrong username or password  please try again\n");
        main();
    }
    printf("login successfull\n");
    contents();
    return 0;
}



// this function displaysthe table of contents
void contents()
{
    int index = 0;
    printf("1. Add Password\n");
    printf("2. Delete Password\n");
    printf("3. View all saved Passwords\n");
    printf("4. Delete all saved Passwords\n");
    printf("5. View last Password\n");
    printf("6. Edit Password\n");
    printf("7. Logout\n");
    printf("8. Exit application\n\n");
    printf("Press the index number to go further.\n");
    scanf("%d", &index);
    switch(index)   //switch case makes the function call
    {
        case 1:
        {
            addPassword();
            break;
        }
        case 2:
        {
            deletePassword();//delPassword();
            break;
        }
        case 3:
        {
            viewAllSavedPasswords();
            break;
        }
        case 4:
        {
            deleteAllSavedPasswords();
            break;
        }
        case 5:
        {
            viewLastPassword();
            break;
        }
        case 6:
        {
            editPassword();
            break;
        }
        case 7:
        {
            main();
            break;
        }
        case 8:
        {
            exit(1);
            break;
        }
        default:
        {
            printf("invalid index value! please enter valid index value\n");
            contents();
        }
    }
    
}
