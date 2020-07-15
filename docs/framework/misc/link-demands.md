---
title: Richieste di collegamento
description: Leggere le informazioni sulle richieste di collegamento, che determinano un controllo di sicurezza durante la compilazione JIT (just-in-Time) ed esaminare solo l'assembly chiamante immediato del codice.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
ms.openlocfilehash: eaf9ee1bb5cd10c724240bacac014503685a0c8c
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309105"
---
# <a name="link-demands"></a><span data-ttu-id="17b7b-103">Richieste di collegamento</span><span class="sxs-lookup"><span data-stu-id="17b7b-103">Link Demands</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="17b7b-104">Una richiesta di collegamento determina l'esecuzione di un controllo di sicurezza in fase di compilazione JIT, durante il quale viene esaminato solo l'assembly chiamante immediato del codice.</span><span class="sxs-lookup"><span data-stu-id="17b7b-104">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="17b7b-105">Il collegamento si verifica quando il codice è associato a un riferimento a un tipo, quale un riferimento a un puntatore a funzione o una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="17b7b-105">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="17b7b-106">Se l'assembly chiamante non dispone delle autorizzazioni sufficienti per collegarsi al codice, il collegamento non viene autorizzato e in fase di caricamento ed esecuzione del codice viene generata un'eccezione di runtime.</span><span class="sxs-lookup"><span data-stu-id="17b7b-106">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="17b7b-107">Le richieste di collegamento possono essere sottoposte a override nelle classi che ereditano dal codice.</span><span class="sxs-lookup"><span data-stu-id="17b7b-107">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="17b7b-108">Un percorso completo dello stack non viene eseguito con questo tipo di richiesta e il codice è ancora suscettibile agli attacchi da attirare.</span><span class="sxs-lookup"><span data-stu-id="17b7b-108">A full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="17b7b-109">Se, ad esempio, un metodo nell'assembly A è protetto da una richiesta di collegamento, un chiamante diretto nell'assembly B viene valutato in base alle autorizzazioni dell'assembly B.  Tuttavia, la richiesta di collegamento non valuterà un metodo nell'assembly C se chiama indirettamente il metodo nell'assembly A utilizzando il metodo nell'assembly B. La richiesta di collegamento specifica solo le autorizzazioni che i chiamanti diretti nell'assembly chiamante immediato devono avere per il collegamento al codice.</span><span class="sxs-lookup"><span data-stu-id="17b7b-109">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="17b7b-110">Non vengono specificate le autorizzazioni necessarie a tutti i chiamanti per l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="17b7b-110">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="17b7b-111">I modificatori di percorso chiamate nello stack <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> e <xref:System.Security.CodeAccessPermission.PermitOnly%2A> non influiscono sulla valutazione delle richieste di collegamento.</span><span class="sxs-lookup"><span data-stu-id="17b7b-111">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="17b7b-112">poiché queste non eseguono una verifica del percorso chiamate nello stack.</span><span class="sxs-lookup"><span data-stu-id="17b7b-112">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="17b7b-113">Se si accede a un metodo protetto da una richiesta di collegamento tramite [Reflection](../reflection-and-codedom/reflection.md), una richiesta di collegamento controlla il chiamante immediato del codice a cui si accede tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="17b7b-113">If a method protected by a link demand is accessed through [Reflection](../reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="17b7b-114">Tale comportamento si verifica sia per l'individuazione che per la chiamata di metodi realizzate mediante reflection.</span><span class="sxs-lookup"><span data-stu-id="17b7b-114">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="17b7b-115">Si supponga, ad esempio, che il codice usi la reflection per restituire un <xref:System.Reflection.MethodInfo> oggetto che rappresenta un metodo protetto da una richiesta di collegamento e quindi passa tale oggetto **MethodInfo** a un altro codice che usa l'oggetto per richiamare il metodo originale.</span><span class="sxs-lookup"><span data-stu-id="17b7b-115">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="17b7b-116">In questo caso, il controllo della richiesta di collegamento si verifica due volte: una volta per il codice che restituisce l'oggetto **MethodInfo** e una volta per il codice che lo richiama.</span><span class="sxs-lookup"><span data-stu-id="17b7b-116">In this case, the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17b7b-117">Una richiesta di collegamento effettuata su un costruttore di classe statico non consente di proteggere il costruttore, poiché i costruttori statici vengono chiamati dal sistema, all'esterno del percorso di esecuzione del codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="17b7b-117">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="17b7b-118">Quando una richiesta di collegamento viene applicata a un'intera classe, tale richiesta non consente quindi di proteggere l'accesso a un costruttore statico, anche se consente di proteggere il resto della classe.</span><span class="sxs-lookup"><span data-stu-id="17b7b-118">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="17b7b-119">Il frammento di codice seguente specifica in modo dichiarativo che a ogni codice collegato al metodo `ReadData` deve essere assegnata l'autorizzazione `CustomPermission`.</span><span class="sxs-lookup"><span data-stu-id="17b7b-119">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="17b7b-120">Questa autorizzazione è un'autorizzazione personalizzata ipotetica e non esiste in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="17b7b-120">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="17b7b-121">La richiesta viene eseguita passando un flag **SecurityAction. LinkDemand** a `CustomPermissionAttribute` .</span><span class="sxs-lookup"><span data-stu-id="17b7b-121">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="17b7b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17b7b-122">See also</span></span>

- [<span data-ttu-id="17b7b-123">Attributes (Attributi)</span><span class="sxs-lookup"><span data-stu-id="17b7b-123">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="17b7b-124">Sicurezza dall'accesso di codice</span><span class="sxs-lookup"><span data-stu-id="17b7b-124">Code Access Security</span></span>](code-access-security.md)
