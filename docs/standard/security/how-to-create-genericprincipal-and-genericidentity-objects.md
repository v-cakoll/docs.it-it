---
title: 'Procedura: Creare oggetti GenericPrincipal e GenericIdentity'
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
ms.openlocfilehash: 0567fd12bee19e860373affdf0fdc286d6d5405a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608063"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="416e5-102">Procedura: Creare oggetti GenericPrincipal e GenericIdentity</span><span class="sxs-lookup"><span data-stu-id="416e5-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>
<span data-ttu-id="416e5-103">È possibile usare la <xref:System.Security.Principal.GenericIdentity> classe in combinazione con il <xref:System.Security.Principal.GenericPrincipal> classe per creare uno schema di autorizzazione che esista indipendentemente da un dominio di Windows.</span><span class="sxs-lookup"><span data-stu-id="416e5-103">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>  
  
### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="416e5-104">Per creare un oggetto GenericPrincipal</span><span class="sxs-lookup"><span data-stu-id="416e5-104">To create a GenericPrincipal object</span></span>  
  
1.  <span data-ttu-id="416e5-105">Creare una nuova istanza della classe di identità e inizializzarla con il nome che si desidera conservare.</span><span class="sxs-lookup"><span data-stu-id="416e5-105">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="416e5-106">Il codice seguente crea un nuovo oggetto **GenericIdentity** e lo inizializza con il nome `MyUser`.</span><span class="sxs-lookup"><span data-stu-id="416e5-106">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>  
  
    ```vb  
    Dim MyIdentity As New GenericIdentity("MyUser")  
    ```  
  
    ```csharp  
    GenericIdentity MyIdentity = new GenericIdentity("MyUser");  
    ```  
  
2.  <span data-ttu-id="416e5-107">Creare una nuova istanza della classe **GenericPrincipal** e inizializzarla con l'oggetto **GenericIdentity** creato in precedenza e una matrice di stringhe che rappresenta i ruoli che si desidera associare a questa entità.</span><span class="sxs-lookup"><span data-stu-id="416e5-107">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="416e5-108">L'esempio di codice seguente specifica una matrice di stringhe che rappresenta un ruolo amministratore e un ruolo utente.</span><span class="sxs-lookup"><span data-stu-id="416e5-108">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="416e5-109">Il **GenericPrincipal** viene quindi inizializzato con il precedente **GenericIdentity** e la matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="416e5-109">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>  
  
    ```vb  
    Dim MyStringArray As String() = {"Manager", "Teller"}  
    DIm MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
    ```  
  
    ```csharp  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal = new GenericPrincipal(MyIdentity, MyStringArray);  
    ```  
  
3.  <span data-ttu-id="416e5-110">Usare il codice seguente per allegare l'entità al thread attuale.</span><span class="sxs-lookup"><span data-stu-id="416e5-110">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="416e5-111">Questo è particolarmente utile nelle situazioni in cui l'entità deve essere convalidata più volte, deve essere convalidata da un altro codice in esecuzione nell'applicazione o deve essere convalidata da un <xref:System.Security.Permissions.PrincipalPermission> oggetto.</span><span class="sxs-lookup"><span data-stu-id="416e5-111">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="416e5-112">Si può comunque eseguire la convalida basata sui ruoli sull'oggetto entità senza allegarlo al thread.</span><span class="sxs-lookup"><span data-stu-id="416e5-112">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="416e5-113">Per maggiori informazioni, vedere [Sostituzione di oggetti Principal](../../../docs/standard/security/replacing-a-principal-object.md).</span><span class="sxs-lookup"><span data-stu-id="416e5-113">For more information, see [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md).</span></span>  
  
    ```vb  
    Thread.CurrentPrincipal = MyPrincipal  
    ```  
  
    ```csharp  
    Thread.CurrentPrincipal = MyPrincipal;  
    ```  
  
## <a name="example"></a><span data-ttu-id="416e5-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="416e5-114">Example</span></span>  
 <span data-ttu-id="416e5-115">L'esempio di codice seguente illustra come creare un'istanza di **GenericPrincipal** e di **GenericIdentity**.</span><span class="sxs-lookup"><span data-stu-id="416e5-115">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="416e5-116">Questo codice visualizza i valori di questi oggetti nella console.</span><span class="sxs-lookup"><span data-stu-id="416e5-116">This code displays the values of these objects to the console.</span></span>  
  
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
  
 <span data-ttu-id="416e5-117">In esecuzione, l'applicazione visualizza un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="416e5-117">When executed, the application displays output similar to the following.</span></span>  
  
```  
The Name is: MyIdentity  
The IsAuthenticated is: True  
Is this a Manager? True  
```  
  
## <a name="see-also"></a><span data-ttu-id="416e5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="416e5-118">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [<span data-ttu-id="416e5-119">Sostituzione di oggetti Principal</span><span class="sxs-lookup"><span data-stu-id="416e5-119">Replacing a Principal Object</span></span>](../../../docs/standard/security/replacing-a-principal-object.md)
- [<span data-ttu-id="416e5-120">Oggetti Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="416e5-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
