---
title: Metodi di estensione
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bfc2e6def94d0830df4a4cdf738cdeef106de9f
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43871212"
---
# <a name="extension-methods"></a>Metodi di estensione
I metodi di estensione sono una funzionalità del linguaggio che consente ai metodi statici di essere chiamato usando la sintassi di chiamata del metodo di istanza. Questi metodi devono richiedere almeno un parametro, che rappresenta l'istanza che è il metodo su cui operare.  
  
 La classe che definisce i metodi di tale estensione è definita come la classe "sponsor" e deve essere dichiarata come statica. Per usare i metodi di estensione, uno è necessario importare lo spazio dei nomi che definisce la classe di sponsor.  
  
 **X AVOID** frivolously che definisce i metodi di estensione, in particolar modo nei tipi non si è proprietari.  
  
 Se si possiede il codice sorgente di un tipo, provare a utilizzare i metodi di istanza normale. Se non si è proprietari e si desidera aggiungere un metodo, prestare molta attenzione. Il libero utilizzo dei metodi di estensione è in grado di affollare l'API di tipi che non sono stati progettati per avere questi metodi.  
  
 **✓ CONSIDER** utilizzando i metodi di estensione in uno dei seguenti scenari:  
  
-   Per fornire supporto funzionalità rilevanti per ogni implementazione di un'interfaccia, se ha funzionalità possono essere scritti in termini di interfaccia principale. Questo avviene perché le implementazioni concrete in caso contrario, non è possibile assegnare alle interfacce. Ad esempio, il `LINQ to Objects` gli operatori vengono implementati come metodi di estensione per tutti i <xref:System.Collections.Generic.IEnumerable%601> tipi. Di conseguenza, qualsiasi `IEnumerable<>` implementazione è automaticamente abilitata per LINQ.  
  
-   Quando un metodo di istanza introdurrebbe una dipendenza da un tipo, ma tale dipendenza causa l'interruzione delle regole di gestione delle dipendenze. Ad esempio, una dipendenza da <xref:System.String> a <xref:System.Uri?displayProperty=nameWithType> non è auspicabile e pertanto `String.ToUri()` metodo di istanza restituzione `System.Uri` sarebbe una progettazione errata da una prospettiva di gestione delle dipendenze. Un metodo di estensione statico `Uri.ToUri(this string str)` restituzione `System.Uri` sarebbe una progettazione molto migliore.  
  
 **X AVOID** che definisce i metodi di estensione su <xref:System.Object?displayProperty=nameWithType>.  
  
 Gli utenti di Visual Basic non saranno in grado di chiamare metodi su riferimenti a oggetti usando la sintassi di metodo di estensione. Visual Basic non supporta la chiamata a metodi quali perché, in Visual Basic, dichiarare un riferimento come oggetto forza tutte le chiamate al metodo in modo da essere in ritardo associato (membro effettivo chiamato è determinata in fase di esecuzione), mentre le associazioni ai metodi di estensione vengono determinate in fase di compilazione (associazione anticipata associato).  
  
 Si noti che la linea guida si applica ad altri linguaggi, in cui è presente lo stesso comportamento di associazione, o in cui non sono supportati i metodi di estensione.  
  
 **X DO NOT** inserire i metodi di estensione nello spazio dei nomi stesso come il tipo esteso a meno che non sia per l'aggiunta di metodi a interfacce o per la gestione delle dipendenze.  
  
 **X AVOID** che definisce due o più metodi di estensione con la stessa firma, anche se si trovano in spazi dei nomi diversi.  
  
 **✓ CONSIDER** che definisce i metodi di estensione nello spazio dei nomi stesso come il tipo esteso se il tipo è un'interfaccia e i metodi di estensione sono concepiti per essere utilizzate in molti o tutti i casi.  
  
 **X DO NOT** definire metodi di estensione che implementa una funzionalità negli spazi dei nomi in genere associati con altre funzionalità. Al contrario, definirli nello spazio dei nomi associato alla funzionalità che a cui appartengono.  
  
 **X AVOID** generico denominazione degli spazi dei nomi dedicato ai metodi di estensione (ad esempio, "estensioni"). Utilizzare un nome descrittivo (ad esempio, "Routing") invece.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
