---
title: Convenzioni di denominazione generali
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
ms.openlocfilehash: ef4a8f571a67477739bbc59d3103ba78dea47177
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635912"
---
# <a name="general-naming-conventions"></a>Convenzioni di denominazione generali

In questa sezione vengono descritte le convenzioni di denominazione generali relative alla scelta delle parole, le linee guida sull'utilizzo di abbreviazioni e acronimi e i suggerimenti su come evitare l'utilizzo di nomi specifici della lingua.

## <a name="word-choice"></a>Scelta delle parole
 ✔️ scegliere nomi di identificatori facilmente leggibili.

 Ad esempio, una `HorizontalAlignment` proprietà denominata è `AlignmentHorizontal`più leggibile in inglese di .

 ✔️ favorire la leggibilità rispetto alla brevità.

 Il nome `CanScrollHorizontally` della `ScrollableX` proprietà è migliore di (un riferimento oscuro all'asse X).

 ❌NON utilizzare caratteri di sottolineatura, trattini o altri caratteri non alfanumerici.

 ❌NON usare la notazione ungherese.

 ❌AVOID utilizzando identificatori in conflitto con parole chiave di linguaggi di programmazione ampiamente utilizzati.

 In base alla regola 4 di Common Language Specification (CLS), tutti i linguaggi conformi devono fornire un meccanismo che consenta l'accesso agli elementi denominati che utilizzano una parola chiave di tale lingua come identificatore. In questo caso, ad esempio, viene utilizzato il segno di escape di C. Tuttavia, è comunque una buona idea evitare parole chiave comuni perché è molto più difficile utilizzare un metodo con la sequenza di escape rispetto a uno senza di esso.

## <a name="using-abbreviations-and-acronyms"></a>Utilizzo di abbreviazioni e acronimi
 ❌NON utilizzare abbreviazioni o contrazioni come parte dei nomi degli identificatori.

 Ad esempio, `GetWindow` utilizzare `GetWin`anziché .

 ❌NON utilizzare acronimi che non sono ampiamente accettati, e anche se lo sono, solo quando necessario.

## <a name="avoiding-language-specific-names"></a>Evitare nomi specifici della lingua
 ✔️ utilizzare nomi semanticamente interessanti anziché parole chiave specifiche del linguaggio per i nomi dei tipi.

 Ad esempio, `GetLength` è un `GetInt`nome migliore di .

 ✔️ utilizzare un nome di tipo CLR generico, anziché un nome specifico del linguaggio, nei rari casi in cui un identificatore non ha alcun significato semantico oltre il tipo.

 Ad esempio, un metodo <xref:System.Int64> di `ToInt64`conversione `ToLong` deve <xref:System.Int64> essere denominato , non (perché `long`è un nome CLR per l'alias specifico di C . Nella tabella seguente vengono presentate diverse tipi di dati di base utilizzando i nomi dei tipi CLR ,così come i nomi di tipo corrispondenti per C .

|C#|Visual Basic|C++|CLR|
|---------|------------------|-----------|---------|
|**sbyte**|**Sbyte**|**char**|**Sbyte**|
|**byte**|**Byte**|**unsigned char**|**Byte**|
|**short**|**Breve**|**short**|**Int16**|
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|
|**Int**|**Intero**|**Int**|**Int32**|
|**uint**|**UInt32 (int32)**|**int senza segno**|**UInt32 (int32)**|
|**Lungo**|**Lungo**|**__int64**|**Int64**|
|**Ulong**|**UInt64 (informazioni in inglese)**|**unsigned __int64**|**UInt64 (informazioni in inglese)**|
|**Galleggiante**|**Singolo**|**Galleggiante**|**Singolo**|
|**double**|**Doppia**|**double**|**Doppia**|
|**bool**|**Boolean**|**bool**|**Boolean**|
|**char**|**Char**|**wchar_t**|**Char**|
|**string**|**Stringa**|**Stringa**|**Stringa**|
|**Oggetto**|**Oggetto**|**Oggetto**|**Oggetto**|

 ✔️ utilizzare un nome comune, ad `value` esempio o `item`, anziché ripetere il nome del tipo, nei rari casi in cui un identificatore non ha un significato semantico e il tipo del parametro non è importante.

## <a name="naming-new-versions-of-existing-apis"></a>Denominazione di nuove versioni delle API esistenti
 ✔️ usare un nome simile all'API precedente quando si creano nuove versioni di un'API esistente.

 Ciò consente di evidenziare la relazione tra le API.

 ✔️ preferisce aggiungere un suffisso anziché un prefisso per indicare una nuova versione di un'API esistente.

 Ciò aiuterà l'individuazione durante l'esplorazione della documentazione o l'utilizzo di IntelliSense.This will assist discovery when browsing documentation, or using IntelliSense. La versione precedente dell'API sarà organizzata vicino alle nuove API, perché la maggior parte dei browser e IntelliSense mostrano gli identificatori in ordine alfabetico.

 ✔️ CONSIDER utilizzando un identificatore nuovo di zecca, ma significativo, invece di aggiungere un suffisso o un prefisso.

 ✔️ usare un suffisso numerico per indicare una nuova versione di un'API esistente, in particolare se il nome esistente dell'API è l'unico nome appropriato (ad esempio, se si tratta di uno standard del settore) e se l'aggiunta di un suffisso significativo (o la modifica del nome) non è un'opzione appropriata.

 ❌NON usare il suffisso "Ex" (o simile) per un identificatore per distinguerlo da una versione precedente della stessa API.

 ✔️ utilizzare il suffisso "64" quando si introducono versioni di API che operano su un numero intero a 64 bit (un intero lungo) anziché un numero intero a 32 bit. È necessario adottare questo approccio solo quando esiste l'API a 32 bit esistente; non farlo per le NUOVE API con solo una versione a 64 bit.

 *Porzioni &copy; 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida per la denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
- [.NET naming conventions for EditorConfig](/visualstudio/ide/editorconfig-naming-conventions) (Convenzioni di denominazione .NET per EditorConfig)
