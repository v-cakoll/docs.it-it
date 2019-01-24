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
author: KrzysztofCwalina
ms.openlocfilehash: ae1b7ce83f6698cef470aabf07a12d89042ab8a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667687"
---
# <a name="general-naming-conventions"></a>Convenzioni di denominazione generali
Questa sezione descrive convenzioni di denominazione generali correlate a scelta delle parole, le linee guida sull'uso di abbreviazioni e gli acronimi e consigli su come evitare di utilizzare nomi specifici del linguaggio.  
  
## <a name="word-choice"></a>Scelta delle parole  
 **✓ DO** scegliere i nomi degli identificatori facilmente leggibili.  
  
 Ad esempio, una proprietà denominata `HorizontalAlignment` risulta più inglese-leggibile rispetto a `AlignmentHorizontal`.  
  
 **✓ DO** privilegiare la leggibilità ragioni di brevità.  
  
 Il nome della proprietà `CanScrollHorizontally` migliore `ScrollableX` (un riferimento all'asse x).  
  
 **X DO NOT** utilizzare caratteri di sottolineatura, trattini o altri caratteri non alfanumerici.  
  
 **X DO NOT** utilizzare la notazione ungherese.  
  
 **X AVOID** utilizzando gli identificatori che sono in conflitto con le parole chiave di ampiamente utilizzato linguaggi di programmazione.  
  
 In base alla regola 4 della specifica CLS (Common Language), tutti i linguaggi conformi a devono fornire un meccanismo che consente l'accesso agli elementi denominati che usano una parola chiave del linguaggio come identificatore. C#, ad esempio, Usa il simbolo come meccanismo di escape in questo caso @. Tuttavia, è comunque consigliabile evitare le parole chiave comuni in quanto è molto più difficile da usare un metodo con la sequenza di escape rispetto a uno senza di essa.  
  
## <a name="using-abbreviations-and-acronyms"></a>Usando gli acronimi e abbreviazioni  
 **X DO NOT** utilizzare abbreviazioni o termini più semplici come parte dei nomi degli identificatori.  
  
 Ad esempio, usare `GetWindow` anziché `GetWin`.  
  
 **X DO NOT** utilizzare acronimi che non sono molto diffusa e anche se sono solo quando necessario.  
  
## <a name="avoiding-language-specific-names"></a>Evitare nomi specifici del linguaggio  
 **✓ DO** utilizzare nomi significativi anziché le parole chiave specifiche della lingua per i nomi dei tipi.  
  
 Ad esempio, `GetLength` è un nome migliore rispetto a `GetInt`.  
  
 **✓ DO** usare un nome di tipo generico di CLR, anziché un nome specifico della lingua, in rari casi in cui un identificatore non ha alcun significato semantico oltre il relativo tipo.  
  
 Ad esempio, un metodo di conversione <xref:System.Int64> devono essere denominate `ToInt64`, non `ToLong` (perché <xref:System.Int64> è un nome CLR per il codice c#-alias specifici `long`). La tabella seguente presenta diversi tipi di dati di base usando i nomi dei tipi CLR (nonché i nomi dei tipi corrispondenti per c#, Visual Basic e C++).  
  
|C#|Visual Basic|C++|CLR|  
|---------|------------------|-----------|---------|  
|**sbyte**|**SByte**|**char**|**SByte**|  
|**byte**|**Byte**|**unsigned char**|**Byte**|  
|**short**|**Short**|**short**|**Int16**|  
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|  
|**int**|**Integer**|**int**|**Int32**|  
|**uint**|**UInt32**|**unsigned int**|**UInt32**|  
|**long**|**Long**|**__int64**|**Int64**|  
|**ulong**|**UInt64**|**unsigned __int64**|**UInt64**|  
|**float**|**Single**|**float**|**Single**|  
|**double**|**Double**|**double**|**Double**|  
|**bool**|**Boolean**|**bool**|**Boolean**|  
|**char**|**Char**|**wchar_t**|**Char**|  
|**string**|**String**|**String**|**String**|  
|**object**|**Oggetto**|**Oggetto**|**Oggetto**|  
  
 **✓ DO** utilizzare un nome comune, ad esempio `value` o `item`, piuttosto che ripetere il nome del tipo, in rari casi in cui un identificatore non ha alcun significato semantico e il tipo del parametro non è importante.  
  
## <a name="naming-new-versions-of-existing-apis"></a>Denominazione di nuove versioni delle API esistente  
 **✓ DO** utilizzare un nome simile all'API precedente durante la creazione di nuove versioni di un'API esistente.  
  
 Ciò consente di evidenziare la relazione tra le API.  
  
 **✓ DO** preferisce aggiunta di un suffisso anziché un prefisso per indicare una nuova versione di un'API esistente.  
  
 Questo aiuterà individuazione quando si Esplora la documentazione, o usando IntelliSense. La versione precedente dell'API sarà organizzata vicino le nuove API, perché la maggior parte dei browser e IntelliSense visualizza gli identificatori in ordine alfabetico.  
  
 **✓ CONSIDER** utilizzando un identificatore di nuovo, ma significativo, anziché aggiungere un prefisso o suffisso.  
  
 **✓ DO** utilizzare un suffisso numerico per indicare una nuova versione di un'API esistente, in particolare se il nome dell'API esistente è l'unico nome appropriato (ad esempio, se è uno standard del settore) e se si aggiungono qualsiasi significativo suffisso (o la modifica del nome) non è un'app opzione ropriate.  
  
 **X DO NOT** utilizzare "Ex" (o una simile) suffisso di un identificatore per distinguerlo da una versione precedente dell'API stessa.  
  
 **✓ DO** utilizzano il suffisso "64" quando si introduce le versioni delle API che operano su un valore integer a 64 bit (un valore long integer) anziché un intero a 32 bit. È sufficiente adottare questo approccio quando è presente l'API di 32 bit esistente. non eseguire questa operazione per la nuove API con solo una versione a 64 bit.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
