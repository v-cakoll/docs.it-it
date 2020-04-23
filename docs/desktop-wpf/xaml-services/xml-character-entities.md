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
ms.openlocfilehash: aff96c5d0ee6bbf2bbe2f9e3b3ae091caa781f7a
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071458"
---
# <a name="xml-character-entities-and-xaml"></a>Entità carattere XML e XAML

XAML usa entità carattere definite in XML per i caratteri speciali. Questo argomento descrive alcune entità carattere specifiche e fornisce considerazioni generali sugli altri concetti XML in XAML.

## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a>Problemi relativi a entità carattere e caratteri di escape univoci in XAML

Il markup XAML in genere usa le stesse entità carattere e sequenze di escape definite in XML.

L'eccezione principale è costituita dalle parentesi graffe ({ e }), che in XAML sono significative in quanto indicano a un processore XAML di interpretare come estensione di markup una sequenza di caratteri racchiusa tra parentesi graffe. Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](markup-extensions-overview.md).

È comunque ancora possibile visualizzare le parentesi come caratteri letterali usando una sequenza di escape caratteristica di XAML, anziché di XML. Per ulteriori informazioni, consultate [ {} Sequenza](escape-sequence-markup-extension.md)di escape - Estensione di markup.

Si noti che\\una barra rovesciata ( ) non richiede una sequenza di escape quando viene gestita come stringa.

## <a name="xml-character-entities"></a>Entità carattere XML

Come indicato in precedenza, la maggior parte delle entità carattere e delle sequenze di escape in genere usate per la scrittura di markup XAML sono definite dal codice XML. Questo argomento non offre l'elenco completo di tali entità; è possibile reperire riferimenti più dettagliati per le entità nella documentazione esterna, ad esempio nelle specifiche XML. Di conseguenza, per praticità, in questo argomento vengono elencate alcune delle entità carattere XML specifiche usate normalmente nel markup XAML.

|Carattere|Entità|Note|
|---------------|------------|-----------|
|& (e commerciale)|\&amp;|Deve essere usato per i valori di attributo e per il contenuto di un elemento.|
|> (carattere maggiore di)|\&gt;|Deve essere utilizzato per un valore di attributo, ma > è accettabile come contenuto di un elemento, purché < non lo preceda.|
|< (carattere minore di)|\&lt;|Deve essere utilizzato per un \< valore di attributo, ma è accettabile come contenuto di un elemento finché > non lo segue.|
|'' (virgolette)|\&quot;|Deve essere usato per un valore di attributo, ma le virgolette (") sono accettabili come contenuto di un elemento. Si noti che gli stessi valori di attributo possono essere racchiusi tra virgolette singole (') o doppie ("); il carattere usato per primo definisce quale tipo di virgolette racchiude il valore di attributo e le altre virgolette potranno quindi essere usate come valore letterale all'interno del valore.|
|' (virgoletta singola)|\&apos;|Deve essere usato per un valore di attributo, ma la virgoletta singola (') è accettabile come contenuto di un elemento. Si noti che gli stessi valori di attributo possono essere racchiusi tra virgolette singole (') o doppie ("); il carattere usato per primo definisce quale tipo di virgolette racchiude il valore di attributo e le altre virgolette potranno quindi essere usate come valore letterale all'interno del valore.|
|(mapping dei caratteri numerici)|&#*[integer]*; o & 'x *[esadecimale]*;|XAML supporta i mapping dei caratteri numerici nella codifica attiva.|
|(spazio unificatore)|&\#160; (presupponendo la codifica UTF-8)|Per elementi di documenti dinamici o elementi che accettano testo, come ad esempio gli oggetti <xref:System.Windows.Controls.TextBox> di WPF, gli spazi unificatori non vengono normalizzati all'esterno del markup e questo vale anche per `xml:space="default"`. Per altre informazioni, vedere [Elaborazione di spazi](white-space-processing.md)vuoti in XAML.|

## <a name="xml-comment-format"></a>Formato di commento XML

XAML usa il formato di commento XML: l'inizio del commento è `<!--`, la fine del commento è `-->,` e la sequenza `--` non deve essere inclusa nel commento.

## <a name="xml-processing-instructions"></a>Istruzioni di elaborazione XML

XAML gestisce le istruzioni di elaborazione XML in conformità alle specifiche XML, in base alle quali le istruzioni devono essere passate. L'elaborazione XAML nei servizi XAML di .NET non usa istruzioni di elaborazione. Gli altri framework esistenti che usano XAML non usano istruzioni di elaborazione di XAML.

## <a name="see-also"></a>Vedere anche

- [Panoramica di XAML (WPF)](../fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Grammatica XamlName](xamlname-grammar.md)
- [Elaborazione degli spazi vuoti in XAML](white-space-processing.md)
