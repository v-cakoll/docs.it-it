---
title: Lo spazio dei nomi o il tipo specificato nelle importazioni '<qualifiedelementname>' non contiene alcun membro pubblico o non è definito
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 8675d9c3b202200c89e12e7a5f51a19d9e3e0e64
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409465"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="7a97d-102">Lo spazio dei nomi o il tipo specificato nelle importazioni '\<qualifiedelementname>' non contiene alcun membro pubblico o non è definito</span><span class="sxs-lookup"><span data-stu-id="7a97d-102">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="7a97d-103">Lo spazio dei nomi o il tipo specificato nelle importazioni ' \<qualifiedelementname> ' non contiene alcun membro pubblico o non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="7a97d-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="7a97d-104">Verificare che lo spazio dei nomi o il tipo sia definito e contenga almeno un membro pubblico.</span><span class="sxs-lookup"><span data-stu-id="7a97d-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="7a97d-105">Verificare che il nome dell'alias non contenga altri alias.</span><span class="sxs-lookup"><span data-stu-id="7a97d-105">Make sure the alias name doesn't contain other aliases.</span></span>

<span data-ttu-id="7a97d-106">Un' `Imports` istruzione specifica un elemento contenitore che non può essere trovato o non definisce `Public` membri.</span><span class="sxs-lookup"><span data-stu-id="7a97d-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>

<span data-ttu-id="7a97d-107">Un *elemento contenitore* può essere uno spazio dei nomi, una classe, una struttura, un modulo, un'interfaccia o un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7a97d-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="7a97d-108">L'elemento contenitore contiene membri, ad esempio variabili, procedure o altri elementi contenenti.</span><span class="sxs-lookup"><span data-stu-id="7a97d-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>

<span data-ttu-id="7a97d-109">Lo scopo dell'importazione è consentire al codice di accedere ai membri dello spazio dei nomi o ai tipi senza doverli qualificare.</span><span class="sxs-lookup"><span data-stu-id="7a97d-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="7a97d-110">Il progetto potrebbe anche dover aggiungere un riferimento allo spazio dei nomi o al tipo.</span><span class="sxs-lookup"><span data-stu-id="7a97d-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="7a97d-111">Per ulteriori informazioni, vedere "importazione di elementi contenitore" in [riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="7a97d-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

<span data-ttu-id="7a97d-112">Se il compilatore non riesce a trovare l'elemento contenitore specificato, non può risolvere i riferimenti che lo usano.</span><span class="sxs-lookup"><span data-stu-id="7a97d-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="7a97d-113">Se trova l'elemento, ma l'elemento non espone `Public` membri, nessun riferimento può avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7a97d-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="7a97d-114">In entrambi i casi non è significativo importare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="7a97d-114">In either case it is meaningless to import the element.</span></span>

<span data-ttu-id="7a97d-115">Tenere presente che se si importa un elemento contenitore e si assegna un alias di importazione, non è possibile usare tale alias di importazione per importare un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="7a97d-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="7a97d-116">Il codice seguente genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="7a97d-116">The following code generates a compiler error.</span></span>

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

<span data-ttu-id="7a97d-117">**ID errore:** BC40056</span><span class="sxs-lookup"><span data-stu-id="7a97d-117">**Error ID:** BC40056</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7a97d-118">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7a97d-118">To correct this error</span></span>

1. <span data-ttu-id="7a97d-119">Verificare che l'elemento contenitore sia accessibile dal progetto.</span><span class="sxs-lookup"><span data-stu-id="7a97d-119">Verify that the containing element is accessible from your project.</span></span>

2. <span data-ttu-id="7a97d-120">Verificare che la specifica dell'elemento contenitore non includa alcun alias di importazione da un'altra importazione.</span><span class="sxs-lookup"><span data-stu-id="7a97d-120">Verify that the specification of the containing element does not include any import alias from another import.</span></span>

3. <span data-ttu-id="7a97d-121">Verificare che l'elemento contenitore esponga almeno un `Public` membro.</span><span class="sxs-lookup"><span data-stu-id="7a97d-121">Verify that the containing element exposes at least one `Public` member.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a97d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a97d-122">See also</span></span>

- [<span data-ttu-id="7a97d-123">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="7a97d-123">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="7a97d-124">Istruzione Namespace</span><span class="sxs-lookup"><span data-stu-id="7a97d-124">Namespace Statement</span></span>](../statements/namespace-statement.md)
- [<span data-ttu-id="7a97d-125">Pubblica</span><span class="sxs-lookup"><span data-stu-id="7a97d-125">Public</span></span>](../modifiers/public.md)
- [<span data-ttu-id="7a97d-126">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a97d-126">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="7a97d-127">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="7a97d-127">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
