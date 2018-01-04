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
ms.workload: dotnet
ms.openlocfilehash: 6b325c931579606f6d1d90eb821766a4110acfd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xml-character-entities-and-xaml"></a><span data-ttu-id="aad1b-102">Entità carattere XML e XAML</span><span class="sxs-lookup"><span data-stu-id="aad1b-102">XML Character Entities and XAML</span></span>
<span data-ttu-id="aad1b-103">XAML usa entità carattere definite in XML per i caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="aad1b-103">XAML uses character entities defined in XML for special characters.</span></span> <span data-ttu-id="aad1b-104">Questo argomento descrive alcune entità carattere specifiche e fornisce considerazioni generali sugli altri concetti XML in XAML.</span><span class="sxs-lookup"><span data-stu-id="aad1b-104">This topic describes some specific character entities and general considerations for other XML concepts in XAML.</span></span>  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a><span data-ttu-id="aad1b-105">Problemi relativi a entità carattere e caratteri di escape univoci in XAML</span><span class="sxs-lookup"><span data-stu-id="aad1b-105">Character Entities and Escaping Issues That Are Unique to XAML</span></span>  
 <span data-ttu-id="aad1b-106">Il markup XAML in genere usa le stesse entità carattere e sequenze di escape definite in XML.</span><span class="sxs-lookup"><span data-stu-id="aad1b-106">XAML markup typically uses the same character entities and escape sequences that are defined in XML.</span></span>  
  
 <span data-ttu-id="aad1b-107">L'eccezione principale è costituita dalle parentesi graffe ({ e }), che in XAML sono significative in quanto indicano a un processore XAML di interpretare come estensione di markup una sequenza di caratteri racchiusa tra parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="aad1b-107">The main exception is that braces ({ and }) have significance in XAML because these characters inform a XAML processor that a character sequence enclosed by braces must be interpreted as a markup extension.</span></span> <span data-ttu-id="aad1b-108">Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aad1b-108">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
 <span data-ttu-id="aad1b-109">È comunque ancora possibile visualizzare le parentesi come caratteri letterali usando una sequenza di escape caratteristica di XAML, anziché di XML.</span><span class="sxs-lookup"><span data-stu-id="aad1b-109">However, you can still display the braces as literal characters by using an escape sequence that is particular to XAML instead of XML.</span></span> <span data-ttu-id="aad1b-110">Per ulteriori informazioni, vedere [{} sequenza di Escape - estensione di Markup](escape-sequence-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="aad1b-110">For more information, see [{} Escape Sequence - Markup Extension](escape-sequence-markup-extension.md).</span></span>  
  
 <span data-ttu-id="aad1b-111">Si noti che una barra rovesciata (\\) non richiede una sequenza di escape quando viene gestita come una stringa.</span><span class="sxs-lookup"><span data-stu-id="aad1b-111">Note that a backslash (\\) does not require an escape sequence when it is handled as a string.</span></span>  
  
<a name="xml_character_entities"></a>   
## <a name="xml-character-entities"></a><span data-ttu-id="aad1b-112">Entità carattere XML</span><span class="sxs-lookup"><span data-stu-id="aad1b-112">XML Character Entities</span></span>  
 <span data-ttu-id="aad1b-113">Come indicato in precedenza, la maggior parte delle entità carattere e delle sequenze di escape in genere usate per la scrittura di markup XAML sono definite dal codice XML.</span><span class="sxs-lookup"><span data-stu-id="aad1b-113">As mentioned previously, most character entities and escape sequences that are typically used to write XAML markup are defined by XML.</span></span> <span data-ttu-id="aad1b-114">Questo argomento non offre l'elenco completo di tali entità; è possibile reperire riferimenti più dettagliati per le entità nella documentazione esterna, ad esempio nelle specifiche XML.</span><span class="sxs-lookup"><span data-stu-id="aad1b-114">This topic does not provide the complete list of these entities; a detailed reference for the entities can be found in external documentation, such as in XML specifications.</span></span> <span data-ttu-id="aad1b-115">Di conseguenza, per praticità, in questo argomento vengono elencate alcune delle entità carattere XML specifiche usate normalmente nel markup XAML.</span><span class="sxs-lookup"><span data-stu-id="aad1b-115">However, for convenience, this topic lists some of the specific XML character entities that are typically used in XAML markup.</span></span>  
  
|<span data-ttu-id="aad1b-116">Carattere</span><span class="sxs-lookup"><span data-stu-id="aad1b-116">Character</span></span>|<span data-ttu-id="aad1b-117">Entità</span><span class="sxs-lookup"><span data-stu-id="aad1b-117">Entity</span></span>|<span data-ttu-id="aad1b-118">Note</span><span class="sxs-lookup"><span data-stu-id="aad1b-118">Notes</span></span>|  
|---------------|------------|-----------|  
|<span data-ttu-id="aad1b-119">& (e commerciale)</span><span class="sxs-lookup"><span data-stu-id="aad1b-119">& (ampersand)</span></span>|<span data-ttu-id="aad1b-120">\&amp;</span><span class="sxs-lookup"><span data-stu-id="aad1b-120">\&amp;</span></span>|<span data-ttu-id="aad1b-121">Deve essere usato per i valori di attributo e per il contenuto di un elemento.</span><span class="sxs-lookup"><span data-stu-id="aad1b-121">Must be used both for attribute values and for content of an element.</span></span>|  
|<span data-ttu-id="aad1b-122">> (carattere maggiore di)</span><span class="sxs-lookup"><span data-stu-id="aad1b-122">> (greater-than character)</span></span>|<span data-ttu-id="aad1b-123">\&gt;</span><span class="sxs-lookup"><span data-stu-id="aad1b-123">\&gt;</span></span>|<span data-ttu-id="aad1b-124">Deve essere usato per un valore di attributo, ma > è accettabile come contenuto di un elemento a condizione che non sia preceduto da <.</span><span class="sxs-lookup"><span data-stu-id="aad1b-124">Must be used for an attribute value, but > is acceptable as the content of an element as long as < does not precede it.</span></span>|  
|<span data-ttu-id="aad1b-125">< (carattere minore di)</span><span class="sxs-lookup"><span data-stu-id="aad1b-125">< (less-than character)</span></span>|<span data-ttu-id="aad1b-126">\&lt;</span><span class="sxs-lookup"><span data-stu-id="aad1b-126">\&lt;</span></span>|<span data-ttu-id="aad1b-127">Deve essere utilizzato per un valore di attributo, ma \< è accettabile come contenuto di un elemento, purché > non è conforme.</span><span class="sxs-lookup"><span data-stu-id="aad1b-127">Must be used for an attribute value, but \< is acceptable as the content of an element as long as > does not follow it.</span></span>|  
|<span data-ttu-id="aad1b-128">'' (virgolette)</span><span class="sxs-lookup"><span data-stu-id="aad1b-128">" (straight quotation mark)</span></span>|<span data-ttu-id="aad1b-129">\&quot;</span><span class="sxs-lookup"><span data-stu-id="aad1b-129">\&quot;</span></span>|<span data-ttu-id="aad1b-130">Deve essere usato per un valore di attributo, ma le virgolette (") sono accettabili come contenuto di un elemento.</span><span class="sxs-lookup"><span data-stu-id="aad1b-130">Must be used for an attribute value, but a straight quotation mark (") is acceptable as the content of an element.</span></span> <span data-ttu-id="aad1b-131">Si noti che gli stessi valori di attributo possono essere racchiusi tra virgolette singole (') o doppie ("); il carattere usato per primo definisce quale tipo di virgolette racchiude il valore di attributo e le altre virgolette potranno quindi essere usate come valore letterale all'interno del valore.</span><span class="sxs-lookup"><span data-stu-id="aad1b-131">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="aad1b-132">' (virgoletta singola)</span><span class="sxs-lookup"><span data-stu-id="aad1b-132">' (single straight quotation mark)</span></span>|<span data-ttu-id="aad1b-133">\&apos;</span><span class="sxs-lookup"><span data-stu-id="aad1b-133">\&apos;</span></span>|<span data-ttu-id="aad1b-134">Deve essere usato per un valore di attributo, ma la virgoletta singola (') è accettabile come contenuto di un elemento.</span><span class="sxs-lookup"><span data-stu-id="aad1b-134">Must be used for an attribute value, but a single straight quotation mark (') is acceptable as the content of an element.</span></span> <span data-ttu-id="aad1b-135">Si noti che gli stessi valori di attributo possono essere racchiusi tra virgolette singole (') o doppie ("); il carattere usato per primo definisce quale tipo di virgolette racchiude il valore di attributo e le altre virgolette potranno quindi essere usate come valore letterale all'interno del valore.</span><span class="sxs-lookup"><span data-stu-id="aad1b-135">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="aad1b-136">(mapping dei caratteri numerici)</span><span class="sxs-lookup"><span data-stu-id="aad1b-136">(numeric character mappings)</span></span>|<span data-ttu-id="aad1b-137">&#*[intero]* ; o & #x*[esadecimale]*;</span><span class="sxs-lookup"><span data-stu-id="aad1b-137">&#*[integer]*; or &#x*[hex]*;</span></span>|<span data-ttu-id="aad1b-138">XAML supporta i mapping dei caratteri numerici nella codifica attiva.</span><span class="sxs-lookup"><span data-stu-id="aad1b-138">XAML supports numeric character mappings into the encoding that is active.</span></span>|  
|<span data-ttu-id="aad1b-139">(spazio unificatore)</span><span class="sxs-lookup"><span data-stu-id="aad1b-139">(nonbreaking space)</span></span>|<span data-ttu-id="aad1b-140">&\#160; (presupponendo che la codifica UTF-8)</span><span class="sxs-lookup"><span data-stu-id="aad1b-140">&\#160; (assuming UTF-8 encoding)</span></span>|<span data-ttu-id="aad1b-141">Per elementi di documenti dinamici o elementi che accettano testo, come ad esempio gli oggetti <xref:System.Windows.Controls.TextBox> di WPF, gli spazi unificatori non vengono normalizzati all'esterno del markup e questo vale anche per `xml:space="default"`.</span><span class="sxs-lookup"><span data-stu-id="aad1b-141">For flow document elements, or elements that take text such as the WPF <xref:System.Windows.Controls.TextBox>, nonbreaking spaces are not normalized out of the markup, even for `xml:space="default"`.</span></span> <span data-ttu-id="aad1b-142">(Per ulteriori informazioni, vedere [elaborazione degli spazi vuoti in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span><span class="sxs-lookup"><span data-stu-id="aad1b-142">(For more information, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span></span>|  
  
<a name="xml_comment_format"></a>   
## <a name="xml-comment-format"></a><span data-ttu-id="aad1b-143">Formato di commento XML</span><span class="sxs-lookup"><span data-stu-id="aad1b-143">XML Comment Format</span></span>  
 <span data-ttu-id="aad1b-144">XAML usa il formato di commento XML: l'inizio del commento è `<!--`, la fine del commento è `-->,` e la sequenza `--` non deve essere inclusa nel commento.</span><span class="sxs-lookup"><span data-stu-id="aad1b-144">XAML uses the XML comment format: the start of the comment is `<!--`, the end of comment is `-->,` and the sequence `--` must not occur within the comment.</span></span>  
  
<a name="xml_processing_instructions"></a>   
## <a name="xml-processing-instructions"></a><span data-ttu-id="aad1b-145">Istruzioni di elaborazione XML</span><span class="sxs-lookup"><span data-stu-id="aad1b-145">XML Processing Instructions</span></span>  
 <span data-ttu-id="aad1b-146">XAML gestisce le istruzioni di elaborazione XML in conformità alle specifiche XML, in base alle quali le istruzioni devono essere passate.</span><span class="sxs-lookup"><span data-stu-id="aad1b-146">XAML handles XML processing instructions according to XML specifications, which state that the instructions must be passed through.</span></span> <span data-ttu-id="aad1b-147">Elaborazione di XAML nei servizi XAML di .NET Framework non usa le istruzioni di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="aad1b-147">XAML processing in .NET Framework XAML Services  does not use any processing instructions.</span></span> <span data-ttu-id="aad1b-148">Gli altri framework esistenti che usano XAML non usano istruzioni di elaborazione di XAML.</span><span class="sxs-lookup"><span data-stu-id="aad1b-148">Other existing frameworks that use XAML also do not use processing instructions from XAML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad1b-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aad1b-149">See Also</span></span>  
 [<span data-ttu-id="aad1b-150">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="aad1b-150">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="aad1b-151">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="aad1b-151">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="aad1b-152">Grammatica XamlName</span><span class="sxs-lookup"><span data-stu-id="aad1b-152">XamlName Grammar</span></span>](../../../docs/framework/xaml-services/xamlname-grammar.md)  
 [<span data-ttu-id="aad1b-153">Elaborazione degli spazi vuoti in XAML</span><span class="sxs-lookup"><span data-stu-id="aad1b-153">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)
