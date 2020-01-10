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
ms.openlocfilehash: 546b4d20f7b6b7a8c448f704fefd9a39b3ebd1d7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706149"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="a6c04-102">Procedura: creare oggetti GenericPrincipal e GenericIdentity</span><span class="sxs-lookup"><span data-stu-id="a6c04-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>

<span data-ttu-id="a6c04-103">È possibile utilizzare la classe <xref:System.Security.Principal.GenericIdentity> insieme alla classe <xref:System.Security.Principal.GenericPrincipal> per creare uno schema di autorizzazione esistente indipendentemente da un dominio di Windows.</span><span class="sxs-lookup"><span data-stu-id="a6c04-103">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>

### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="a6c04-104">Per creare un oggetto GenericPrincipal</span><span class="sxs-lookup"><span data-stu-id="a6c04-104">To create a GenericPrincipal object</span></span>

1. <span data-ttu-id="a6c04-105">Creare una nuova istanza della classe di identità e inizializzarla con il nome che si desidera conservare.</span><span class="sxs-lookup"><span data-stu-id="a6c04-105">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="a6c04-106">Il codice seguente crea un nuovo oggetto **GenericIdentity** e lo inizializza con il nome `MyUser`.</span><span class="sxs-lookup"><span data-stu-id="a6c04-106">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. <span data-ttu-id="a6c04-107">Creare una nuova istanza della classe **GenericPrincipal** e inizializzarla con l'oggetto **GenericIdentity** creato in precedenza e una matrice di stringhe che rappresenta i ruoli che si desidera associare a questa entità.</span><span class="sxs-lookup"><span data-stu-id="a6c04-107">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="a6c04-108">L'esempio di codice seguente specifica una matrice di stringhe che rappresenta un ruolo amministratore e un ruolo utente.</span><span class="sxs-lookup"><span data-stu-id="a6c04-108">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="a6c04-109">Il **GenericPrincipal** viene quindi inizializzato con il precedente **GenericIdentity** e la matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="a6c04-109">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. <span data-ttu-id="a6c04-110">Usare il codice seguente per allegare l'entità al thread attuale.</span><span class="sxs-lookup"><span data-stu-id="a6c04-110">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="a6c04-111">Questo è utile nelle situazioni in cui l'entità deve essere convalidata più volte, deve essere convalidata da un altro codice in esecuzione nell'applicazione oppure deve essere convalidata da un oggetto <xref:System.Security.Permissions.PrincipalPermission>.</span><span class="sxs-lookup"><span data-stu-id="a6c04-111">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="a6c04-112">Si può comunque eseguire la convalida basata sui ruoli sull'oggetto entità senza allegarlo al thread.</span><span class="sxs-lookup"><span data-stu-id="a6c04-112">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="a6c04-113">Per maggiori informazioni, vedere [Sostituzione di oggetti Principal](../../../docs/standard/security/replacing-a-principal-object.md).</span><span class="sxs-lookup"><span data-stu-id="a6c04-113">For more information, see [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md).</span></span>

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a><span data-ttu-id="a6c04-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6c04-114">Example</span></span>

<span data-ttu-id="a6c04-115">L'esempio di codice seguente illustra come creare un'istanza di **GenericPrincipal** e di **GenericIdentity**.</span><span class="sxs-lookup"><span data-stu-id="a6c04-115">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="a6c04-116">Questo codice visualizza i valori di questi oggetti nella console.</span><span class="sxs-lookup"><span data-stu-id="a6c04-116">This code displays the values of these objects to the console.</span></span>

```vb
Imports System.Security.Principal
Imports System.Threading

Public Class Class1

    Public Shared Sub Main()
        ' Create generic identity.
        Dim myIdentity As New GenericIdentity("MyIdentity")

        ' Create generic principal.
        Dim myStringArray As String() =  {"Manager", "Teller"}
        Dim myPrincipal As New GenericPrincipal(myIdentity, myStringArray)

        ' Attach the principal to the current thread.
        ' This is not required unless repeated validation must occur,
        ' other code in your application must validate, or the
        ' PrincipalPermission object is used.
        Thread.CurrentPrincipal = myPrincipal

        ' Print values to the console.
        Dim name As String = myPrincipal.Identity.Name
        Dim auth As Boolean = myPrincipal.Identity.IsAuthenticated
        Dim isInRole As Boolean = myPrincipal.IsInRole("Manager")

        Console.WriteLine("The name is: {0}", name)
        Console.WriteLine("The isAuthenticated is: {0}", auth)
        Console.WriteLine("Is this a Manager? {0}", isInRole)

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
    GenericIdentity myIdentity = new GenericIdentity("MyIdentity");

    // Create generic principal.
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal =
        new GenericPrincipal(myIdentity, myStringArray);

    // Attach the principal to the current thread.
    // This is not required unless repeated validation must occur,
    // other code in your application must validate, or the
    // PrincipalPermission object is used.
    Thread.CurrentPrincipal = myPrincipal;

    // Print values to the console.
    String name =  myPrincipal.Identity.Name;
    bool auth =  myPrincipal.Identity.IsAuthenticated;
    bool isInRole =  myPrincipal.IsInRole("Manager");

    Console.WriteLine("The name is: {0}", name);
    Console.WriteLine("The isAuthenticated is: {0}", auth);
    Console.WriteLine("Is this a Manager? {0}", isInRole);

    return 0;
    }
}
```

<span data-ttu-id="a6c04-117">In esecuzione, l'applicazione visualizza un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="a6c04-117">When executed, the application displays output similar to the following.</span></span>

```console
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a><span data-ttu-id="a6c04-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6c04-118">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [<span data-ttu-id="a6c04-119">Sostituzione di oggetti Principal</span><span class="sxs-lookup"><span data-stu-id="a6c04-119">Replacing a Principal Object</span></span>](../../../docs/standard/security/replacing-a-principal-object.md)
- [<span data-ttu-id="a6c04-120">Oggetti Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="a6c04-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
