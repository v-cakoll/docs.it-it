---
title: WriteOnly
ms.date: 07/20/2015
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
ms.openlocfilehash: a9fa0a3a23561215d6ff122bc8e609b68ca6fc30
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386634"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="aa19c-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa19c-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="aa19c-103">Specifica che una proprietà può essere scritta ma non letta.</span><span class="sxs-lookup"><span data-stu-id="aa19c-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa19c-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="aa19c-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="aa19c-105">Regole</span><span class="sxs-lookup"><span data-stu-id="aa19c-105">Rules</span></span>  
 <span data-ttu-id="aa19c-106">\*\*Contesto della dichiarazione. \*\*</span><span class="sxs-lookup"><span data-stu-id="aa19c-106">**Declaration Context.**</span></span> <span data-ttu-id="aa19c-107">Si può usare `WriteOnly` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="aa19c-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="aa19c-108">Ciò significa che il contesto di dichiarazione per una `WriteOnly` proprietà deve essere una classe, una struttura o un modulo e non può essere un file di origine, uno spazio dei nomi o una procedura.</span><span class="sxs-lookup"><span data-stu-id="aa19c-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="aa19c-109">È possibile dichiarare una proprietà come `WriteOnly` , ma non come variabile.</span><span class="sxs-lookup"><span data-stu-id="aa19c-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="aa19c-110">Quando usare WriteOnly</span><span class="sxs-lookup"><span data-stu-id="aa19c-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="aa19c-111">In alcuni casi si vuole che il codice consumer sia in grado di impostare un valore, ma non di individuarne lo stato.</span><span class="sxs-lookup"><span data-stu-id="aa19c-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="aa19c-112">Ad esempio, i dati sensibili, ad esempio un numero di registrazione sociale o una password, devono essere protetti dall'accesso da parte di qualsiasi componente che non lo ha impostato.</span><span class="sxs-lookup"><span data-stu-id="aa19c-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="aa19c-113">In questi casi, è possibile usare una `WriteOnly` proprietà per impostare il valore.</span><span class="sxs-lookup"><span data-stu-id="aa19c-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="aa19c-114">Quando si definisce e si usa una `WriteOnly` proprietà, tenere presenti le misure di protezione aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa19c-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="aa19c-115">**Override.**</span><span class="sxs-lookup"><span data-stu-id="aa19c-115">**Overriding.**</span></span> <span data-ttu-id="aa19c-116">Se la proprietà è un membro di una classe, consentire l'impostazione predefinita di [NotOverridable](notoverridable.md)e non dichiararla `Overridable` o `MustOverride` .</span><span class="sxs-lookup"><span data-stu-id="aa19c-116">If the property is a member of a class, allow it to default to [NotOverridable](notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="aa19c-117">In questo modo si impedisce a una classe derivata di effettuare l'accesso indesiderato tramite una sostituzione.</span><span class="sxs-lookup"><span data-stu-id="aa19c-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="aa19c-118">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="aa19c-118">**Access Level.**</span></span> <span data-ttu-id="aa19c-119">Se si mantengono i dati sensibili della proprietà in una o più variabili, dichiararli [privati](private.md) in modo che nessun altro codice possa accedervi.</span><span class="sxs-lookup"><span data-stu-id="aa19c-119">If you hold the property's sensitive data in one or more variables, declare them [Private](private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="aa19c-120">**Crittografia.**</span><span class="sxs-lookup"><span data-stu-id="aa19c-120">**Encryption.**</span></span> <span data-ttu-id="aa19c-121">Archiviare tutti i dati sensibili in formato crittografato anziché in testo normale.</span><span class="sxs-lookup"><span data-stu-id="aa19c-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="aa19c-122">Se il codice dannoso in qualche modo può accedere a tale area della memoria, è più difficile usare i dati.</span><span class="sxs-lookup"><span data-stu-id="aa19c-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="aa19c-123">La crittografia è utile anche se è necessario serializzare i dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="aa19c-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="aa19c-124">**Ripristino.**</span><span class="sxs-lookup"><span data-stu-id="aa19c-124">**Resetting.**</span></span> <span data-ttu-id="aa19c-125">Quando la classe, la struttura o il modulo che definisce la proprietà viene terminato, reimpostare i dati sensibili sui valori predefiniti o su altri valori non significativi.</span><span class="sxs-lookup"><span data-stu-id="aa19c-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="aa19c-126">Questo garantisce una protezione aggiuntiva quando l'area di memoria viene liberata per l'accesso generale.</span><span class="sxs-lookup"><span data-stu-id="aa19c-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="aa19c-127">**Persistenza.**</span><span class="sxs-lookup"><span data-stu-id="aa19c-127">**Persistence.**</span></span> <span data-ttu-id="aa19c-128">Non rende permanente i dati sensibili, ad esempio su disco, se è possibile evitarli.</span><span class="sxs-lookup"><span data-stu-id="aa19c-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="aa19c-129">Inoltre, non scrivere dati sensibili negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="aa19c-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="aa19c-130">Il `WriteOnly` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="aa19c-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="aa19c-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="aa19c-131">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="aa19c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa19c-132">See also</span></span>

- [<span data-ttu-id="aa19c-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="aa19c-133">ReadOnly</span></span>](readonly.md)
- [<span data-ttu-id="aa19c-134">Privata</span><span class="sxs-lookup"><span data-stu-id="aa19c-134">Private</span></span>](private.md)
- [<span data-ttu-id="aa19c-135">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="aa19c-135">Keywords</span></span>](../keywords/index.md)
