---
title: WriteOnly (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9dab9115c31e538bd28583b9f0591ae0c9611e2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="6ff04-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ff04-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="6ff04-103">Specifica che è possibile scritta una proprietà ma non è stato letto.</span><span class="sxs-lookup"><span data-stu-id="6ff04-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ff04-104">Note</span><span class="sxs-lookup"><span data-stu-id="6ff04-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="6ff04-105">Regole</span><span class="sxs-lookup"><span data-stu-id="6ff04-105">Rules</span></span>  
 <span data-ttu-id="6ff04-106">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="6ff04-106">**Declaration Context.**</span></span> <span data-ttu-id="6ff04-107">Si può usare `WriteOnly` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="6ff04-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="6ff04-108">Ciò significa che il contesto della dichiarazione per un `WriteOnly` proprietà deve essere una classe, struttura o modulo e non può essere un file di origine, lo spazio dei nomi o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="6ff04-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="6ff04-109">È possibile dichiarare una proprietà come `WriteOnly`, ma non una variabile.</span><span class="sxs-lookup"><span data-stu-id="6ff04-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="6ff04-110">Quando utilizzare WriteOnly</span><span class="sxs-lookup"><span data-stu-id="6ff04-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="6ff04-111">Talvolta il codice in grado di impostare un valore senza scoprire che cos'è utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6ff04-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="6ff04-112">Ad esempio, i dati sensibili, ad esempio un codice fiscale o una password, debbano essere protetti dall'accesso da qualsiasi componente che non è stata impostata.</span><span class="sxs-lookup"><span data-stu-id="6ff04-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="6ff04-113">In questi casi, è possibile utilizzare un `WriteOnly` proprietà per impostare il valore.</span><span class="sxs-lookup"><span data-stu-id="6ff04-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6ff04-114">Quando si definisce e utilizzare un `WriteOnly` proprietà, considerare le misure di protezione aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ff04-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
-   <span data-ttu-id="6ff04-115">**Si esegue l'override.**</span><span class="sxs-lookup"><span data-stu-id="6ff04-115">**Overriding.**</span></span> <span data-ttu-id="6ff04-116">Se la proprietà è un membro di una classe, per impostazione predefinita per consentire [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)e non dichiararla `Overridable` o `MustOverride`.</span><span class="sxs-lookup"><span data-stu-id="6ff04-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="6ff04-117">Ciò impedisce che una classe derivata effettua l'accesso indesiderato tramite una sostituzione.</span><span class="sxs-lookup"><span data-stu-id="6ff04-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
-   <span data-ttu-id="6ff04-118">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="6ff04-118">**Access Level.**</span></span> <span data-ttu-id="6ff04-119">Se sono contenuti dati sensibili della proprietà in una o più variabili, dichiarare [privata](../../../visual-basic/language-reference/modifiers/private.md) in modo che nessun altro codice possa accedervi.</span><span class="sxs-lookup"><span data-stu-id="6ff04-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
-   <span data-ttu-id="6ff04-120">**Crittografia.**</span><span class="sxs-lookup"><span data-stu-id="6ff04-120">**Encryption.**</span></span> <span data-ttu-id="6ff04-121">Archiviare tutti i dati sensibili in forma crittografata anziché in testo normale.</span><span class="sxs-lookup"><span data-stu-id="6ff04-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="6ff04-122">Se il codice dannoso in qualche modo accede a tale area di memoria, è difficile utilizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="6ff04-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="6ff04-123">La crittografia è utile anche se è necessario serializzare i dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="6ff04-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
-   <span data-ttu-id="6ff04-124">**Il ripristino.**</span><span class="sxs-lookup"><span data-stu-id="6ff04-124">**Resetting.**</span></span> <span data-ttu-id="6ff04-125">Quando la classe, struttura o modulo che definisce la proprietà viene terminato, reimpostare i dati sensibili sui valori predefiniti o ad altri valori non significativi.</span><span class="sxs-lookup"><span data-stu-id="6ff04-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="6ff04-126">Ciò fornisce una protezione aggiuntiva quando tale area di memoria viene liberata per l'accesso generale.</span><span class="sxs-lookup"><span data-stu-id="6ff04-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
-   <span data-ttu-id="6ff04-127">**Persistenza.**</span><span class="sxs-lookup"><span data-stu-id="6ff04-127">**Persistence.**</span></span> <span data-ttu-id="6ff04-128">Tutti i dati riservati, ad esempio su disco, non vengono mantenute se non è possibile evitare.</span><span class="sxs-lookup"><span data-stu-id="6ff04-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="6ff04-129">Inoltre, non scrivere i dati sensibili negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="6ff04-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="6ff04-130">Il `WriteOnly` modificatore può essere utilizzato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="6ff04-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="6ff04-131">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="6ff04-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ff04-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ff04-132">See Also</span></span>  
 [<span data-ttu-id="6ff04-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="6ff04-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [<span data-ttu-id="6ff04-134">Private</span><span class="sxs-lookup"><span data-stu-id="6ff04-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="6ff04-135">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6ff04-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
