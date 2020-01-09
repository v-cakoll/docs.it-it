---
title: Metodi di estensione
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 2578fbacecd9fe790f72e828b455e8983b1298d3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709361"
---
# <a name="extension-methods"></a>Metodi di estensione
I metodi di estensione sono una funzionalità del linguaggio che consente la chiamata di metodi statici usando la sintassi di chiamata al metodo di istanza. Questi metodi devono assumere almeno un parametro, che rappresenta l'istanza su cui il metodo sta operando.  
  
 La classe che definisce tali metodi di estensione è detta classe "sponsor" e deve essere dichiarata come statica. Per usare i metodi di estensione, è necessario importare lo spazio dei nomi che definisce la classe sponsor.  
  
 **X AVOID** frivolously che definisce i metodi di estensione, in particolar modo nei tipi non si è proprietari.  
  
 Se si esegue il codice sorgente di un tipo, è consigliabile usare invece i metodi di istanza normali. Se non si è proprietari e si desidera aggiungere un metodo, prestare molta attenzione. L'uso dei metodi di estensione in modo liberario può comportare l'utilizzo di API di tipi non progettati per avere questi metodi.  
  
 **✓ CONSIDER** utilizzando i metodi di estensione in uno dei seguenti scenari:  
  
- Per fornire funzionalità di supporto rilevanti per ogni implementazione di un'interfaccia, se detta funzionalità può essere scritta in termini di interfaccia di base. Questo perché le implementazioni concrete non possono essere altrimenti assegnate alle interfacce. Gli operatori `LINQ to Objects`, ad esempio, vengono implementati come metodi di estensione per tutti i tipi di <xref:System.Collections.Generic.IEnumerable%601>. Qualsiasi implementazione di `IEnumerable<>` viene quindi abilitata automaticamente per LINQ.  
  
- Quando un metodo di istanza introduce una dipendenza da un certo tipo, ma tale dipendenza interrompe le regole di gestione delle dipendenze. Ad esempio, una dipendenza da <xref:System.String> a <xref:System.Uri?displayProperty=nameWithType> non è probabilmente auspicabile e pertanto `String.ToUri()` metodo di istanza che restituisce `System.Uri` sarebbe la progettazione sbagliata da una prospettiva di gestione delle dipendenze. Un metodo di estensione statico `Uri.ToUri(this string str)` la restituzione di `System.Uri` sarebbe una progettazione molto migliore.  
  
 **X AVOID** che definisce i metodi di estensione su <xref:System.Object?displayProperty=nameWithType>.  
  
 Visual Basic utenti non saranno in grado di chiamare tali metodi sui riferimenti a oggetti utilizzando la sintassi del metodo di estensione. Visual Basic non supporta la chiamata di tali metodi perché, in Visual Basic, la dichiarazione di un riferimento come oggetto forza l'associazione tardiva di tutte le chiamate al metodo (il membro effettivo chiamato viene determinato in fase di esecuzione), mentre le associazioni ai metodi di estensione sono determinate in tempo di compilazione (associazione anticipata).  
  
 Si noti che le linee guida si applicano ad altre lingue in cui è presente lo stesso comportamento di associazione o se i metodi di estensione non sono supportati.  
  
 **X DO NOT** inserire i metodi di estensione nello spazio dei nomi stesso come il tipo esteso a meno che non sia per l'aggiunta di metodi a interfacce o per la gestione delle dipendenze.  
  
 **X AVOID** che definisce due o più metodi di estensione con la stessa firma, anche se si trovano in spazi dei nomi diversi.  
  
 **✓ CONSIDER** che definisce i metodi di estensione nello spazio dei nomi stesso come il tipo esteso se il tipo è un'interfaccia e i metodi di estensione sono concepiti per essere utilizzate in molti o tutti i casi.  
  
 **X DO NOT** definire metodi di estensione che implementa una funzionalità negli spazi dei nomi in genere associati con altre funzionalità. Definire invece tali elementi nello spazio dei nomi associato alla funzionalità a cui appartengono.  
  
 **X AVOID** generico denominazione degli spazi dei nomi dedicato ai metodi di estensione (ad esempio, "estensioni"). Usare invece un nome descrittivo (ad esempio, "routing").  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
