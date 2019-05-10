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
ms.openlocfilehash: f6898008fa3e3e7e385a2bc77c5b2eac7eeda2ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617148"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="08139-102">Tipo XAML intrinseco x:Code</span><span class="sxs-lookup"><span data-stu-id="08139-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="08139-103">Consente il posizionamento del codice all'interno di una produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="08139-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="08139-104">Tale codice può essere compilato da qualsiasi implementazione di processore XAML che consente la compilazione XAML o a sinistra in produzione XAML per utilizzi successivi, ad esempio interpretazione da un runtime.</span><span class="sxs-lookup"><span data-stu-id="08139-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="08139-105">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="08139-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="08139-106">Note</span><span class="sxs-lookup"><span data-stu-id="08139-106">Remarks</span></span>  
 <span data-ttu-id="08139-107">Il codice all'interno di `x:Code` elemento della direttiva XAML viene sempre interpretato nello spazio dei nomi XML generale e gli spazi dei nomi XAML specificato.</span><span class="sxs-lookup"><span data-stu-id="08139-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="08139-108">Pertanto, in genere è necessario racchiudere il codice usato per `x:Code` all'interno di un `CDATA` segmento.</span><span class="sxs-lookup"><span data-stu-id="08139-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="08139-109">`x:Code` non è consentito per tutti i possibili meccanismi di distribuzione di una produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="08139-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="08139-110">Il codice deve essere compilato nel framework specifici (ad esempio WPF).</span><span class="sxs-lookup"><span data-stu-id="08139-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="08139-111">In altri Framework, `x:Code` utilizzo potrebbe essere impedito a livello generale.</span><span class="sxs-lookup"><span data-stu-id="08139-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="08139-112">Per i framework che consentono a managed `x:Code` il contenuto, il compilatore di linguaggio corretto da usare per `x:Code` contenuto è determinato dalle impostazioni e le destinazioni del progetto che lo contiene viene usato per compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="08139-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="08139-113">Note sull'utilizzo WPF</span><span class="sxs-lookup"><span data-stu-id="08139-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="08139-114">Codice dichiarati all'interno di `x:Code` per WPF ha alcune limitazioni rilevanti:</span><span class="sxs-lookup"><span data-stu-id="08139-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
- <span data-ttu-id="08139-115">Il `x:Code` elemento della direttiva deve essere un elemento figlio immediato dell'elemento radice della produzione XAML.</span><span class="sxs-lookup"><span data-stu-id="08139-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
- <span data-ttu-id="08139-116">[Direttiva X:Class](x-class-directive.md) deve essere fornita per l'elemento radice padre.</span><span class="sxs-lookup"><span data-stu-id="08139-116">[x:Class Directive](x-class-directive.md) must be provided on the parent root element.</span></span>  
  
- <span data-ttu-id="08139-117">Il codice inserito all'interno di `x:Code` verrà considerato dalla compilazione per rientrare nell'ambito della classe parziale che è già creata per la pagina XAML.</span><span class="sxs-lookup"><span data-stu-id="08139-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="08139-118">Di conseguenza deve essere tutto il codice che è definire membri o le variabili di tale classe parziale.</span><span class="sxs-lookup"><span data-stu-id="08139-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
- <span data-ttu-id="08139-119">Non è possibile definire altre classi, diverso da una classe all'interno della classe parziale di annidamento (è consentito l'annidamento, ma non accade in genere perché le classi annidate non possono essere fatto riferimento in XAML).</span><span class="sxs-lookup"><span data-stu-id="08139-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="08139-120">Spazi dei nomi CLR nomi diverso da quello utilizzato per la classe parziale esistente non può essere definita o aggiungere.</span><span class="sxs-lookup"><span data-stu-id="08139-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
- <span data-ttu-id="08139-121">I riferimenti alle entità di codice all'esterno dello spazio dei nomi CLR classe parziale devono essere completi.</span><span class="sxs-lookup"><span data-stu-id="08139-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="08139-122">Se i membri dichiarati sono gli override per i membri di classe parziale sottoponibile a override, questo deve essere specificato con la parola chiave override specifico del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="08139-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="08139-123">Se i membri dichiarati `x:Code` ambito sono in conflitto con i membri della classe parziale creato di fuori di XAML, in modo che il compilatore segnala il conflitto, il file XAML non è possibile compilare o caricare.</span><span class="sxs-lookup"><span data-stu-id="08139-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08139-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08139-124">See also</span></span>

- [<span data-ttu-id="08139-125">Direttiva x:Class</span><span class="sxs-lookup"><span data-stu-id="08139-125">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="08139-126">Code-behind e XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="08139-126">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="08139-127">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="08139-127">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
