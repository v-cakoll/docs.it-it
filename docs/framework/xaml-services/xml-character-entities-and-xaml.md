---
title: "Entità carattere XML e XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '&'
- '&amp'
- '&gt'
- '&lt'
helpviewer_keywords:
- XAML [XAML Services], special characters
- ampersand (&) [XAML Services]
- special characters [XAML Services]
- apostrophe (') [XAML Services]
- greater-than (>) character [XAML Services]
- XAML [XAML Services], quotation mark (")
- XAML [XAML Services], apostrophe (')
- '& (ampersand) [XAML Services]'
- XAML [XAML Services], & (ampersand)
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- less-than (<) character [XAML Services]
ms.assetid: 6896d0ce-74f7-420a-9ab4-de9bbf390e8d
caps.latest.revision: "23"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 5973c67b26e07bba69383cc625ff34493d825a41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-character-entities-and-xaml"></a><span data-ttu-id="dc396-102">Entità carattere XML e XAML</span><span class="sxs-lookup"><span data-stu-id="dc396-102">XML Character Entities and XAML</span></span>
<span data-ttu-id="dc396-103">XAML usa entità carattere definite in XML per i caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="dc396-103">XAML uses character entities defined in XML for special characters.</span></span> <span data-ttu-id="dc396-104">Questo argomento descrive alcune entità carattere specifiche e fornisce considerazioni generali sugli altri concetti XML in XAML.</span><span class="sxs-lookup"><span data-stu-id="dc396-104">This topic describes some specific character entities and general considerations for other XML concepts in XAML.</span></span>  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a><span data-ttu-id="dc396-105">Problemi relativi a entità carattere e caratteri di escape univoci in XAML</span><span class="sxs-lookup"><span data-stu-id="dc396-105">Character Entities and Escaping Issues That Are Unique to XAML</span></span>  
 <span data-ttu-id="dc396-106">Il markup XAML in genere usa le stesse entità carattere e sequenze di escape definite in XML.</span><span class="sxs-lookup"><span data-stu-id="dc396-106">XAML markup typically uses the same character entities and escape sequences that are defined in XML.</span></span>  
  
 <span data-ttu-id="dc396-107">L'eccezione principale è costituita dalle parentesi graffe ({ e }), che in XAML sono significative in quanto indicano a un processore XAML di interpretare come estensione di markup una sequenza di caratteri racchiusa tra parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="dc396-107">The main exception is that braces ({ and }) have significance in XAML because these characters inform a XAML processor that a character sequence enclosed by braces must be interpreted as a markup extension.</span></span> <span data-ttu-id="dc396-108">Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dc396-108">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
 <span data-ttu-id="dc396-109">È comunque ancora possibile visualizzare le parentesi come caratteri letterali usando una sequenza di escape caratteristica di XAML, anziché di XML.</span><span class="sxs-lookup"><span data-stu-id="dc396-109">However, you can still display the braces as literal characters by using an escape sequence that is particular to XAML instead of XML.</span></span> <span data-ttu-id="dc396-110">Per ulteriori informazioni, vedere [{} sequenza di Escape - estensione di Markup](escape-sequence-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="dc396-110">For more information, see [{} Escape Sequence - Markup Extension](escape-sequence-markup-extension.md).</span></span>  
  
 <span data-ttu-id="dc396-111">Si noti che una barra rovesciata (\\) non richiede una sequenza di escape quando viene gestita come una stringa.</span><span class="sxs-lookup"><span data-stu-id="dc396-111">Note that a backslash (\\) does not require an escape sequence when it is handled as a string.</span></span>  
  
<a name="xml_character_entities"></a>   
## <a name="xml-character-entities"></a><span data-ttu-id="dc396-112">Entità carattere XML</span><span class="sxs-lookup"><span data-stu-id="dc396-112">XML Character Entities</span></span>  
 <span data-ttu-id="dc396-113">Come indicato in precedenza, la maggior parte delle entità carattere e delle sequenze di escape in genere usate per la scrittura di markup XAML sono definite dal codice XML.</span><span class="sxs-lookup"><span data-stu-id="dc396-113">As mentioned previously, most character entities and escape sequences that are typically used to write XAML markup are defined by XML.</span></span> <span data-ttu-id="dc396-114">Questo argomento non offre l'elenco completo di tali entità; è possibile reperire riferimenti più dettagliati per le entità nella documentazione esterna, ad esempio nelle specifiche XML.</span><span class="sxs-lookup"><span data-stu-id="dc396-114">This topic does not provide the complete list of these entities; a detailed reference for the entities can be found in external documentation, such as in XML specifications.</span></span> <span data-ttu-id="dc396-115">Di conseguenza, per praticità, in questo argomento vengono elencate alcune delle entità carattere XML specifiche usate normalmente nel markup XAML.</span><span class="sxs-lookup"><span data-stu-id="dc396-115">However, for convenience, this topic lists some of the specific XML character entities that are typically used in XAML markup.</span></span>  
  
|<span data-ttu-id="dc396-116">Carattere</span><span class="sxs-lookup"><span data-stu-id="dc396-116">Character</span></span>|<span data-ttu-id="dc396-117">Entità</span><span class="sxs-lookup"><span data-stu-id="dc396-117">Entity</span></span>|<span data-ttu-id="dc396-118">Note</span><span class="sxs-lookup"><span data-stu-id="dc396-118">Notes</span></span>|  
|---------------|------------|-----------|  
|<span data-ttu-id="dc396-119">& (e commerciale)</span><span class="sxs-lookup"><span data-stu-id="dc396-119">& (ampersand)</span></span>|&amp;|<span data-ttu-id="dc396-120">Deve essere usato per i valori di attributo e per il contenuto di un elemento.</span><span class="sxs-lookup"><span data-stu-id="dc396-120">Must be used both for attribute values and for content of an element.</span></span>|  
|<span data-ttu-id="dc396-121">> (carattere maggiore di)</span><span class="sxs-lookup"><span data-stu-id="dc396-121">> (greater-than character)</span></span>|&gt;|<span data-ttu-id="dc396-122">Deve essere usato per un valore di attributo, ma > è accettabile come contenuto di un elemento a condizione che non sia preceduto da <.</span><span class="sxs-lookup"><span data-stu-id="dc396-122">Must be used for an attribute value, but > is acceptable as the content of an element as long as < does not precede it.</span></span>|  
|<span data-ttu-id="dc396-123">< (carattere minore di)</span><span class="sxs-lookup"><span data-stu-id="dc396-123">< (less-than character)</span></span>|&lt;|<span data-ttu-id="dc396-124">Deve essere utilizzato per un valore di attributo, ma \< è accettabile come contenuto di un elemento, purché > non è conforme.</span><span class="sxs-lookup"><span data-stu-id="dc396-124">Must be used for an attribute value, but \< is acceptable as the content of an element as long as > does not follow it.</span></span>|  
|<span data-ttu-id="dc396-125">'' (virgolette)</span><span class="sxs-lookup"><span data-stu-id="dc396-125">" (straight quotation mark)</span></span>|&quot;|<span data-ttu-id="dc396-126">Deve essere usato per un valore di attributo, ma le virgolette (") sono accettabili come contenuto di un elemento.</span><span class="sxs-lookup"><span data-stu-id="dc396-126">Must be used for an attribute value, but a straight quotation mark (") is acceptable as the content of an element.</span></span> <span data-ttu-id="dc396-127">Si noti che gli stessi valori di attributo possono essere racchiusi tra virgolette singole (') o doppie ("); il carattere usato per primo definisce quale tipo di virgolette racchiude il valore di attributo e le altre virgolette potranno quindi essere usate come valore letterale all'interno del valore.</span><span class="sxs-lookup"><span data-stu-id="dc396-127">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="dc396-128">' (virgoletta singola)</span><span class="sxs-lookup"><span data-stu-id="dc396-128">' (single straight quotation mark)</span></span>|&apos;|<span data-ttu-id="dc396-129">Deve essere usato per un valore di attributo, ma la virgoletta singola (') è accettabile come contenuto di un elemento.</span><span class="sxs-lookup"><span data-stu-id="dc396-129">Must be used for an attribute value, but a single straight quotation mark (') is acceptable as the content of an element.</span></span> <span data-ttu-id="dc396-130">Si noti che gli stessi valori di attributo possono essere racchiusi tra virgolette singole (') o doppie ("); il carattere usato per primo definisce quale tipo di virgolette racchiude il valore di attributo e le altre virgolette potranno quindi essere usate come valore letterale all'interno del valore.</span><span class="sxs-lookup"><span data-stu-id="dc396-130">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="dc396-131">(mapping dei caratteri numerici)</span><span class="sxs-lookup"><span data-stu-id="dc396-131">(numeric character mappings)</span></span>|<span data-ttu-id="dc396-132">&#*[intero]* ; o & #x*[esadecimale]*;</span><span class="sxs-lookup"><span data-stu-id="dc396-132">&#*[integer]*; or &#x*[hex]*;</span></span>|<span data-ttu-id="dc396-133">XAML supporta i mapping dei caratteri numerici nella codifica attiva.</span><span class="sxs-lookup"><span data-stu-id="dc396-133">XAML supports numeric character mappings into the encoding that is active.</span></span>|  
|<span data-ttu-id="dc396-134">(spazio unificatore)</span><span class="sxs-lookup"><span data-stu-id="dc396-134">(nonbreaking space)</span></span>|<span data-ttu-id="dc396-135">&\#160; (presupponendo che la codifica UTF-8)</span><span class="sxs-lookup"><span data-stu-id="dc396-135">&\#160; (assuming UTF-8 encoding)</span></span>|<span data-ttu-id="dc396-136">Per elementi di documenti dinamici o elementi che accettano testo, come ad esempio gli oggetti <xref:System.Windows.Controls.TextBox> di WPF, gli spazi unificatori non vengono normalizzati all'esterno del markup e questo vale anche per `xml:space="default"`.</span><span class="sxs-lookup"><span data-stu-id="dc396-136">For flow document elements, or elements that take text such as the WPF <xref:System.Windows.Controls.TextBox>, nonbreaking spaces are not normalized out of the markup, even for `xml:space="default"`.</span></span> <span data-ttu-id="dc396-137">(Per ulteriori informazioni, vedere [elaborazione degli spazi vuoti in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span><span class="sxs-lookup"><span data-stu-id="dc396-137">(For more information, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span></span>|  
  
<a name="xml_comment_format"></a>   
## <a name="xml-comment-format"></a><span data-ttu-id="dc396-138">Formato di commento XML</span><span class="sxs-lookup"><span data-stu-id="dc396-138">XML Comment Format</span></span>  
 <span data-ttu-id="dc396-139">XAML usa il formato di commento XML: l'inizio del commento è `<!--`, la fine del commento è `-->,` e la sequenza `--` non deve essere inclusa nel commento.</span><span class="sxs-lookup"><span data-stu-id="dc396-139">XAML uses the XML comment format: the start of the comment is `<!--`, the end of comment is `-->,` and the sequence `--` must not occur within the comment.</span></span>  
  
<a name="xml_processing_instructions"></a>   
## <a name="xml-processing-instructions"></a><span data-ttu-id="dc396-140">Istruzioni di elaborazione XML</span><span class="sxs-lookup"><span data-stu-id="dc396-140">XML Processing Instructions</span></span>  
 <span data-ttu-id="dc396-141">XAML gestisce le istruzioni di elaborazione XML in conformità alle specifiche XML, in base alle quali le istruzioni devono essere passate.</span><span class="sxs-lookup"><span data-stu-id="dc396-141">XAML handles XML processing instructions according to XML specifications, which state that the instructions must be passed through.</span></span> <span data-ttu-id="dc396-142">Elaborazione di XAML nei servizi XAML di .NET Framework non usa le istruzioni di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="dc396-142">XAML processing in .NET Framework XAML Services  does not use any processing instructions.</span></span> <span data-ttu-id="dc396-143">Gli altri framework esistenti che usano XAML non usano istruzioni di elaborazione di XAML.</span><span class="sxs-lookup"><span data-stu-id="dc396-143">Other existing frameworks that use XAML also do not use processing instructions from XAML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc396-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc396-144">See Also</span></span>  
 [<span data-ttu-id="dc396-145">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="dc396-145">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="dc396-146">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="dc396-146">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="dc396-147">Grammatica XamlName</span><span class="sxs-lookup"><span data-stu-id="dc396-147">XamlName Grammar</span></span>](../../../docs/framework/xaml-services/xamlname-grammar.md)  
 [<span data-ttu-id="dc396-148">Elaborazione degli spazi vuoti in XAML</span><span class="sxs-lookup"><span data-stu-id="dc396-148">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)
