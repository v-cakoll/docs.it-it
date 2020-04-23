---
title: Tipo XAML intrinseco x:Code
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071556"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="d1f95-102">Tipo XAML intrinseco x:Code</span><span class="sxs-lookup"><span data-stu-id="d1f95-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="d1f95-103">Consente il posizionamento del codice all'interno di una produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="d1f95-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="d1f95-104">Tale codice può essere compilato da qualsiasi implementazione del processore XAML che compila XAML o lasciato nella produzione XAML per usi successivi, ad esempio l'interpretazione da parte di un runtime.</span><span class="sxs-lookup"><span data-stu-id="d1f95-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="d1f95-105">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="d1f95-105">XAML Object Element Usage</span></span>

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a><span data-ttu-id="d1f95-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d1f95-106">Remarks</span></span>

<span data-ttu-id="d1f95-107">Il codice `x:Code` all'interno dell'elemento della direttiva XAML viene comunque interpretato all'interno dello spazio dei nomi XML generale e degli spazi dei nomi XAML forniti.</span><span class="sxs-lookup"><span data-stu-id="d1f95-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="d1f95-108">Pertanto, è in genere necessario `x:Code` racchiudere `CDATA` il codice utilizzato per l'interno di un segmento.</span><span class="sxs-lookup"><span data-stu-id="d1f95-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>

<span data-ttu-id="d1f95-109">`x:Code`non è consentito per tutti i possibili meccanismi di distribuzione di una produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="d1f95-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="d1f95-110">In framework specifici (ad esempio WPFWPF) il codice deve essere compilato.</span><span class="sxs-lookup"><span data-stu-id="d1f95-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="d1f95-111">In altri framework, `x:Code` l'utilizzo potrebbe essere in genere non consentito.</span><span class="sxs-lookup"><span data-stu-id="d1f95-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>

<span data-ttu-id="d1f95-112">Per i framework `x:Code` che consentono il contenuto gestito, il compilatore di linguaggio corretto da utilizzare per `x:Code` il contenuto è determinato dalle impostazioni e dalle destinazioni del progetto contenitore utilizzato per compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d1f95-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="d1f95-113">Note sull'utilizzo di WPF</span><span class="sxs-lookup"><span data-stu-id="d1f95-113">WPF Usage Notes</span></span>

<span data-ttu-id="d1f95-114">Il codice `x:Code` dichiarato all'interno di WPFWPF presenta diverse limitazioni notevoli:Code declared within within for WPF has several notable limitations:</span><span class="sxs-lookup"><span data-stu-id="d1f95-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>

- <span data-ttu-id="d1f95-115">L'elemento `x:Code` della direttiva deve essere un elemento figlio immediato dell'elemento radice della produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="d1f95-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>

- <span data-ttu-id="d1f95-116">[X:Class Direttiva](xclass-directive.md) deve essere fornito nell'elemento radice padre.</span><span class="sxs-lookup"><span data-stu-id="d1f95-116">[x:Class Directive](xclass-directive.md) must be provided on the parent root element.</span></span>

- <span data-ttu-id="d1f95-117">Il codice `x:Code` inserito all'interno verrà considerato dalla compilazione nell'ambito della classe parziale già creata per la pagina XAML.</span><span class="sxs-lookup"><span data-stu-id="d1f95-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="d1f95-118">Pertanto tutto il codice definito deve essere membri o variabili di tale classe parziale.</span><span class="sxs-lookup"><span data-stu-id="d1f95-118">Therefore all code you define must be members or variables of that partial class.</span></span>

- <span data-ttu-id="d1f95-119">Non è possibile definire classi aggiuntive, se non annidando una classe all'interno della classe parziale (l'annidamento è consentito, ma non è tipico perché non è possibile fare riferimento alle classi annidate in XAML).</span><span class="sxs-lookup"><span data-stu-id="d1f95-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="d1f95-120">Gli spazi dei nomi CLR diversi dallo spazio dei nomi utilizzato per la classe parziale esistente non possono essere definiti o aggiunti.</span><span class="sxs-lookup"><span data-stu-id="d1f95-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>

- <span data-ttu-id="d1f95-121">I riferimenti alle entità di codice all'esterno dello spazio dei nomi CLR della classe parziale devono essere tutti completi.</span><span class="sxs-lookup"><span data-stu-id="d1f95-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="d1f95-122">Se i membri dichiarati sono override per la classe parziale sottoponibili a override, questo deve essere specificato con la parola chiave override specifica del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="d1f95-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="d1f95-123">Se i `x:Code` membri dichiarati nell'ambito sono in conflitto con i membri della classe parziale creata dal codice XAML, in modo che il compilatore segnala il conflitto, il file XAML non può compilare o caricare.</span><span class="sxs-lookup"><span data-stu-id="d1f95-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1f95-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1f95-124">See also</span></span>

- [<span data-ttu-id="d1f95-125">Direttiva x:Class</span><span class="sxs-lookup"><span data-stu-id="d1f95-125">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="d1f95-126">Code-behind e XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="d1f95-126">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="d1f95-127">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d1f95-127">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
