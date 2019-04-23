---
title: Entità carattere XML e XAML
ms.date: 03/30/2017
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
ms.openlocfilehash: b4621da21200e6c9e2b174a0e2ba508a4f6bab92
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228198"
---
# <a name="xml-character-entities-and-xaml"></a>Entità carattere XML e XAML
XAML usa entità carattere definite in XML per i caratteri speciali. Questo argomento descrive alcune entità carattere specifiche e fornisce considerazioni generali sugli altri concetti XML in XAML.  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a>Problemi relativi a entità carattere e caratteri di escape univoci in XAML  
 Il markup XAML in genere usa le stesse entità carattere e sequenze di escape definite in XML.  
  
 L'eccezione principale è costituita dalle parentesi graffe ({ e }), che in XAML sono significative in quanto indicano a un processore XAML di interpretare come estensione di markup una sequenza di caratteri racchiusa tra parentesi graffe. Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).  
  
 È comunque ancora possibile visualizzare le parentesi come caratteri letterali usando una sequenza di escape caratteristica di XAML, anziché di XML. Per altre informazioni, vedere [ {} sequenza di Escape - estensione di Markup](escape-sequence-markup-extension.md).  
  
 Si noti che una barra rovesciata (\\) non richiede una sequenza di escape quando viene gestita come una stringa.  
  
<a name="xml_character_entities"></a>   
## <a name="xml-character-entities"></a>Entità carattere XML  
 Come indicato in precedenza, la maggior parte delle entità carattere e delle sequenze di escape in genere usate per la scrittura di markup XAML sono definite dal codice XML. Questo argomento non offre l'elenco completo di tali entità; è possibile reperire riferimenti più dettagliati per le entità nella documentazione esterna, ad esempio nelle specifiche XML. Di conseguenza, per praticità, in questo argomento vengono elencate alcune delle entità carattere XML specifiche usate normalmente nel markup XAML.  
  
|Carattere|Entità|Note|  
|---------------|------------|-----------|  
|& (e commerciale)|\&amp;|Deve essere usato per i valori di attributo e per il contenuto di un elemento.|  
|> (maggiore-carattere maggiore di)|\&gt;|Deve essere usato per un valore di attributo, ma > è accettabile come contenuto di un elemento, purché < non sia preceduto da.|  
|< (minore-carattere maggiore di)|\&lt;|Deve essere usato per un valore di attributo, ma \< è accettabile come contenuto di un elemento, purché > non è conforme.|  
|'' (virgolette)|\&quot;|Deve essere usato per un valore di attributo, ma le virgolette (") sono accettabili come contenuto di un elemento. Si noti che gli stessi valori di attributo possono essere racchiusi tra virgolette singole (') o doppie ("); il carattere usato per primo definisce quale tipo di virgolette racchiude il valore di attributo e le altre virgolette potranno quindi essere usate come valore letterale all'interno del valore.|  
|' (virgoletta singola)|\&apos;|Deve essere usato per un valore di attributo, ma la virgoletta singola (') è accettabile come contenuto di un elemento. Si noti che gli stessi valori di attributo possono essere racchiusi tra virgolette singole (') o doppie ("); il carattere usato per primo definisce quale tipo di virgolette racchiude il valore di attributo e le altre virgolette potranno quindi essere usate come valore letterale all'interno del valore.|  
|(mapping dei caratteri numerici)|&#*[intero]* ; o & #x10 *[esadecimale]*;|XAML supporta i mapping dei caratteri numerici nella codifica attiva.|  
|(spazio unificatore)|&\#160; (presupponendo che la codifica UTF-8)|Per elementi di documenti dinamici o elementi che accettano testo, come ad esempio gli oggetti <xref:System.Windows.Controls.TextBox> di WPF, gli spazi unificatori non vengono normalizzati all'esterno del markup e questo vale anche per `xml:space="default"`. (Per altre informazioni, vedere [l'elaborazione in XAML gli spazi vuoti](whitespace-processing-in-xaml.md).)|  
  
<a name="xml_comment_format"></a>   
## <a name="xml-comment-format"></a>Formato di commento XML  
 XAML usa il formato di commento XML: l'inizio del commento è `<!--`, la fine del commento è `-->,` e la sequenza `--` non deve essere inclusa nel commento.  
  
<a name="xml_processing_instructions"></a>   
## <a name="xml-processing-instructions"></a>Istruzioni di elaborazione XML  
 XAML gestisce le istruzioni di elaborazione XML in conformità alle specifiche XML, in base alle quali le istruzioni devono essere passate. XAML nei servizi XAML di .NET Framework di elaborazione non usa le istruzioni di elaborazione. Gli altri framework esistenti che usano XAML non usano istruzioni di elaborazione di XAML.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Grammatica XamlName](xamlname-grammar.md)
- [L'elaborazione in XAML gli spazi vuoti](whitespace-processing-in-xaml.md)
