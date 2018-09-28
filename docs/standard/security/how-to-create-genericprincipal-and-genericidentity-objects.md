---
title: 'Procedura: creare oggetti GenericPrincipal e GenericIdentity'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Creating Generic Identity Objects
- GenericPrincipal Objects
- Creating GenericPrincipal Objects
- GenericIdentity Objects
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 79b5e05fe9133eb2282eedefa001e64ece5e0f57
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2018
ms.locfileid: "47421138"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a>Procedura: creare oggetti GenericPrincipal e GenericIdentity
È possibile usare la <xref:System.Security.Principal.GenericIdentity> classe in combinazione con il <xref:System.Security.Principal.GenericPrincipal> classe per creare uno schema di autorizzazione che esista indipendentemente da un dominio di Windows.  
  
### <a name="to-create-a-genericprincipal-object"></a>Per creare un oggetto GenericPrincipal  
  
1.  Creare una nuova istanza della classe di identità e inizializzarla con il nome che si desidera conservare. Il codice seguente crea un nuovo oggetto **GenericIdentity** e lo inizializza con il nome `MyUser`.  
  
    ```vb  
    Dim MyIdentity As New GenericIdentity("MyUser")  
    ```  
  
    ```csharp  
    GenericIdentity MyIdentity = new GenericIdentity("MyUser");  
    ```  
  
2.  Creare una nuova istanza della classe **GenericPrincipal** e inizializzarla con l'oggetto **GenericIdentity** creato in precedenza e una matrice di stringhe che rappresenta i ruoli che si desidera associare a questa entità. L'esempio di codice seguente specifica una matrice di stringhe che rappresenta un ruolo amministratore e un ruolo utente. Il **GenericPrincipal** viene quindi inizializzato con il precedente **GenericIdentity** e la matrice di stringhe.  
  
    ```vb  
    Dim MyStringArray As String() = {"Manager", "Teller"}  
    DIm MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
    ```  
  
    ```csharp  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal = new GenericPrincipal(MyIdentity, MyStringArray);  
    ```  
  
3.  Usare il codice seguente per allegare l'entità al thread attuale. Questo è particolarmente utile nelle situazioni in cui l'entità deve essere convalidata più volte, deve essere convalidata da un altro codice in esecuzione nell'applicazione o deve essere convalidata da un <xref:System.Security.Permissions.PrincipalPermission> oggetto. Si può comunque eseguire la convalida basata sui ruoli sull'oggetto entità senza allegarlo al thread. Per maggiori informazioni, vedere [Sostituzione di oggetti Principal](../../../docs/standard/security/replacing-a-principal-object.md).  
  
    ```vb  
    Thread.CurrentPrincipal = MyPrincipal  
    ```  
  
    ```csharp  
    Thread.CurrentPrincipal = MyPrincipal;  
    ```  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come creare un'istanza di **GenericPrincipal** e di **GenericIdentity**. Questo codice visualizza i valori di questi oggetti nella console.  
  
```vb  
Imports System  
Imports System.Security.Principal  
Imports System.Threading  
  
Public Class Class1  
  
    Public Shared Sub Main()  
        ' Create generic identity.  
        Dim MyIdentity As New GenericIdentity("MyIdentity")  
  
        ' Create generic principal.  
        Dim MyStringArray As String() =  {"Manager", "Teller"}  
        Dim MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
  
        ' Attach the principal to the current thread.  
        ' This is not required unless repeated validation must occur,  
        ' other code in your application must validate, or the   
        ' PrincipalPermisson object is used.   
        Thread.CurrentPrincipal = MyPrincipal  
  
        ' Print values to the console.  
        Dim Name As String = MyPrincipal.Identity.Name  
        Dim Auth As Boolean = MyPrincipal.Identity.IsAuthenticated  
        Dim IsInRole As Boolean = MyPrincipal.IsInRole("Manager")  
  
        Console.WriteLine("The Name is: {0}", Name)  
        Console.WriteLine("The IsAuthenticated is: {0}", Auth)  
        Console.WriteLine("Is this a Manager? {0}", IsInRole)  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Security.Principal;  
using System.Threading;  
  
public class Class1  
{  
    public static int Main(string[] args)  
    {  
    // Create generic identity.  
    GenericIdentity MyIdentity = new GenericIdentity("MyIdentity");  
  
    // Create generic principal.  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal =   
        new GenericPrincipal(MyIdentity, MyStringArray);  
  
    // Attach the principal to the current thread.  
    // This is not required unless repeated validation must occur,  
    // other code in your application must validate, or the   
    // PrincipalPermisson object is used.   
    Thread.CurrentPrincipal = MyPrincipal;  
  
    // Print values to the console.  
    String Name =  MyPrincipal.Identity.Name;  
    bool Auth =  MyPrincipal.Identity.IsAuthenticated;   
    bool IsInRole =  MyPrincipal.IsInRole("Manager");  
  
    Console.WriteLine("The Name is: {0}", Name);  
    Console.WriteLine("The IsAuthenticated is: {0}", Auth);  
    Console.WriteLine("Is this a Manager? {0}", IsInRole);  
  
    return 0;  
    }  
}  
```  
  
 In esecuzione, l'applicazione visualizza un output simile al seguente.  
  
```  
The Name is: MyIdentity  
The IsAuthenticated is: True  
Is this a Manager? True  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Principal.GenericIdentity>  
- <xref:System.Security.Principal.GenericPrincipal>  
- <xref:System.Security.Permissions.PrincipalPermission>  
- [Sostituzione di oggetti Principal](../../../docs/standard/security/replacing-a-principal-object.md)  
- [Oggetti Principal e Identity](../../../docs/standard/security/principal-and-identity-objects.md)
