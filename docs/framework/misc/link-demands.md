---
title: Richieste di collegamento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: faeeabeda89ea233e67b66b8848f5bbb665d3804
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="link-demands"></a><span data-ttu-id="92498-102">Richieste di collegamento</span><span class="sxs-lookup"><span data-stu-id="92498-102">Link Demands</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="92498-103">Una richiesta di collegamento determina l'esecuzione di un controllo di sicurezza in fase di compilazione JIT, durante il quale viene esaminato solo l'assembly chiamante immediato del codice.</span><span class="sxs-lookup"><span data-stu-id="92498-103">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="92498-104">Il collegamento si verifica quando il codice è associato a un riferimento a un tipo, quale un riferimento a un puntatore a funzione o una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="92498-104">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="92498-105">Se l'assembly chiamante non dispone delle autorizzazioni sufficienti per collegarsi al codice, il collegamento non viene autorizzato e in fase di caricamento ed esecuzione del codice viene generata un'eccezione di runtime.</span><span class="sxs-lookup"><span data-stu-id="92498-105">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="92498-106">Le richieste di collegamento possono essere sottoposte a override nelle classi che ereditano dal codice.</span><span class="sxs-lookup"><span data-stu-id="92498-106">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="92498-107">Mediante questo tipo di richiesta non viene eseguita un'analisi completa dello stack e permane il rischio che il codice sia soggetto ad attacchi subdoli.</span><span class="sxs-lookup"><span data-stu-id="92498-107">Note that a full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="92498-108">Ad esempio, se un metodo nell'assembly A è protetto da una richiesta di collegamento, un chiamante diretto nell'assembly B viene valutato in base alle autorizzazioni dell'Assembly B.  Tuttavia, la richiesta di collegamento non restituirà un metodo nell'assembly C se indirettamente chiama il metodo nell'assembly utilizzando il metodo nell'assembly B. La richiesta di collegamento specifica che solo le autorizzazioni di indirizzare i chiamanti nell'assembly chiamante immediato devono disporre di collegamento al codice.</span><span class="sxs-lookup"><span data-stu-id="92498-108">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="92498-109">Non vengono specificate le autorizzazioni necessarie a tutti i chiamanti per l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="92498-109">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="92498-110">I modificatori di percorso chiamate nello stack <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> e <xref:System.Security.CodeAccessPermission.PermitOnly%2A> non influiscono sulla valutazione delle richieste di collegamento.</span><span class="sxs-lookup"><span data-stu-id="92498-110">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="92498-111">poiché queste non eseguono una verifica del percorso chiamate nello stack.</span><span class="sxs-lookup"><span data-stu-id="92498-111">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="92498-112">Se un metodo protetto da una richiesta di collegamento si accede tramite [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md), quindi una richiesta di collegamento viene controllato il chiamante immediato del codice tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="92498-112">If a method protected by a link demand is accessed through [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="92498-113">Tale comportamento si verifica sia per l'individuazione che per la chiamata di metodi realizzate mediante reflection.</span><span class="sxs-lookup"><span data-stu-id="92498-113">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="92498-114">Si supponga ad esempio di codice utilizza la reflection per restituire un <xref:System.Reflection.MethodInfo> dell'oggetto che rappresenta un metodo protetto da una richiesta di collegamento e viene quindi passato **MethodInfo** oggetto ad altro codice che utilizza l'oggetto per richiamare il metodo originale.</span><span class="sxs-lookup"><span data-stu-id="92498-114">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="92498-115">In questo caso il controllo della richiesta di collegamento viene eseguito due volte: una volta per il codice che restituisce il **MethodInfo** oggetto e una volta per il codice che lo richiama.</span><span class="sxs-lookup"><span data-stu-id="92498-115">In this case the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92498-116">Una richiesta di collegamento effettuata su un costruttore di classe statico non consente di proteggere il costruttore, poiché i costruttori statici vengono chiamati dal sistema, all'esterno del percorso di esecuzione del codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="92498-116">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="92498-117">Quando una richiesta di collegamento viene applicata a un'intera classe, tale richiesta non consente quindi di proteggere l'accesso a un costruttore statico, anche se consente di proteggere il resto della classe.</span><span class="sxs-lookup"><span data-stu-id="92498-117">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="92498-118">Il frammento di codice seguente specifica in modo dichiarativo che a ogni codice collegato al metodo `ReadData` deve essere assegnata l'autorizzazione `CustomPermission`.</span><span class="sxs-lookup"><span data-stu-id="92498-118">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="92498-119">Questa autorizzazione è un'autorizzazione personalizzata ipotetica e non esiste in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="92498-119">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="92498-120">La richiesta viene eseguita passando un **SecurityAction. LinkDemand** flag per il `CustomPermissionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="92498-120">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="92498-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92498-121">See Also</span></span>  
 [<span data-ttu-id="92498-122">Attributi</span><span class="sxs-lookup"><span data-stu-id="92498-122">Attributes</span></span>](../../../docs/standard/attributes/index.md)  
 [<span data-ttu-id="92498-123">Sicurezza dall'accesso di codice</span><span class="sxs-lookup"><span data-stu-id="92498-123">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
