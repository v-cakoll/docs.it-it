---
title: Metodi di estensione
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15d36cc2d3073c9f695de81407ecabcd5e3bba30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="extension-methods"></a>Metodi di estensione
Metodi di estensione rappresentano una funzionalità del linguaggio che consente di metodi statici per chiamare utilizzando la sintassi di chiamata del metodo di istanza. Questi metodi devono accettare almeno un parametro, che rappresenta l'istanza che è il metodo su cui operare.  
  
 La classe che definisce i metodi di tale estensione è definita come la classe "sponsor" e deve essere dichiarata come statica. Per utilizzare i metodi di estensione, uno necessario importare lo spazio dei nomi che definisce la classe sponsor.  
  
 **X evitare** frivolously che definisce i metodi di estensione, in particolar modo nei tipi non si è proprietari.  
  
 Se si è proprietari di codice sorgente di un tipo, provare a utilizzare i normali metodi di istanza. Se non si è proprietari e si desidera aggiungere un metodo, prestare molta attenzione. Il libero utilizzo di metodi di estensione è potenzialmente ingombrare l'API di tipi che non sono stati progettati per disporre di questi metodi.  
  
 **✓ Provare a** utilizzando i metodi di estensione in uno dei seguenti scenari:  
  
-   Per fornire supporto funzionalità rilevanti per ogni implementazione di un'interfaccia, se ha funzionalità possono essere scritti in termini di interfaccia principale. In questo modo le implementazioni concrete in caso contrario non è possibile assegnare alle interfacce. Ad esempio, il `LINQ to Objects` gli operatori vengono implementati come metodi di estensione per tutti i <xref:System.Collections.Generic.IEnumerable%601> tipi. Pertanto, qualsiasi `IEnumerable<>` implementazione è automaticamente abilitato per LINQ.  
  
-   Quando un metodo di istanza introdurrebbe una dipendenza su un tipo, ma tale dipendenza causa l'interruzione di regole di gestione di dipendenza. Ad esempio, una dipendenza da <xref:System.String> per <xref:System.Uri?displayProperty=nameWithType> probabilmente non è consigliabile e pertanto `String.ToUri()` il metodo di istanza restituzione `System.Uri` sarebbe la progettazione errata da una prospettiva di gestione di dipendenza. Un metodo di estensione statici `Uri.ToUri(this string str)` restituzione `System.Uri` sarebbe migliore progettazione.  
  
 **X evitare** che definisce i metodi di estensione su <xref:System.Object?displayProperty=nameWithType>.  
  
 Gli utenti di Visual Basic non saranno in grado di chiamare tali metodi nei riferimenti agli oggetti utilizzando la sintassi del metodo di estensione. Visual Basic non supporta la chiamata di questi metodi perché, in Visual Basic, dichiarare un riferimento come oggetto forza tutte le chiamate di metodo in modo da essere tardiva associato (membro effettivo chiamato viene determinata in fase di esecuzione), mentre le associazioni ai metodi di estensione vengono determinate in fase di compilazione (associazione anticipata associato).  
  
 Si noti che la linea guida si applica ad altri linguaggi, in cui è presente lo stesso comportamento di associazione, o in cui non sono supportati i metodi di estensione.  
  
 **X non** inserire i metodi di estensione nello spazio dei nomi stesso come il tipo esteso a meno che non sia per l'aggiunta di metodi a interfacce o per la gestione delle dipendenze.  
  
 **X evitare** che definisce due o più metodi di estensione con la stessa firma, anche se si trovano in spazi dei nomi diversi.  
  
 **✓ Provare a** che definisce i metodi di estensione nello spazio dei nomi stesso come il tipo esteso se il tipo è un'interfaccia e i metodi di estensione sono concepiti per essere utilizzate in molti o tutti i casi.  
  
 **X non** definire metodi di estensione che implementa una funzionalità negli spazi dei nomi in genere associati con altre funzionalità. Invece, definirli nello spazio dei nomi associato alla funzionalità a che cui appartengono.  
  
 **X evitare** generico denominazione degli spazi dei nomi dedicato ai metodi di estensione (ad esempio, "estensioni"). Utilizzare un nome descrittivo (ad esempio, "Routing") invece.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
