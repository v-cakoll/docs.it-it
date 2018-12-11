---
title: Nomi di spazi dei nomi
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
author: KrzysztofCwalina
ms.openlocfilehash: 64efdc46583a0931df9f57c32424ca4233bf2b82
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143441"
---
# <a name="names-of-namespaces"></a>Nomi di spazi dei nomi
Come con altre convenzioni di denominazione, l'obiettivo per la denominazione degli spazi dei nomi consiste nel creare chiarezza sufficiente per il programmatore usando il framework immediatamente sapere che cos'è probabile che il contenuto dello spazio dei nomi. Il modello seguente specifica la regola generale per la denominazione degli spazi dei nomi:  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 Di seguito è riportati esempi:  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 **✓ DO** spazi dei nomi con un nome della società per evitare gli spazi dei nomi di società diverse da con lo stesso nome del prefisso.  
  
 **✓ DO** utilizzare un nome stabile e indipendente dalla versione del prodotto nel secondo livello di uno spazio dei nomi.  
  
 **X DO NOT** utilizzare gerarchie organizzative come base per i nomi nelle gerarchie dello spazio dei nomi, perché i nomi dei gruppi all'interno di aziende tendono a essere di breve durata. Organizzare la gerarchia di spazi dei nomi intorno a gruppi di tecnologie correlate.  
  
 **✓ DO** utilizzare il sistema Pascal e i componenti di spazio dei nomi separato con punti (ad esempio, `Microsoft.Office.PowerPoint`). Se il vostro marchio impiega le maiuscole e minuscole non convenzionale, è consigliabile seguire le maiuscole e minuscole definite per il tuo marchio, anche se esso devia dal maiuscole e minuscole normale dello spazio dei nomi.  
  
 **✓ CONSIDER** usando nomi plurali ove appropriato.  
  
 Ad esempio, usare `System.Collections` invece di `System.Collection`. Nomi di marchi e gli acronimi sono tuttavia eccezioni a questa regola. Ad esempio, usare `System.IO` invece di `System.IOs`.  
  
 **X DO NOT** utilizzare lo stesso nome per uno spazio dei nomi e un tipo nello spazio dei nomi.  
  
 Ad esempio, non usare `Debug` come uno spazio dei nomi un nome e quindi fornire anche una classe denominata `Debug` nello spazio dei nomi stesso. Alcuni compilatori richiedono tali tipi devono essere completi.  
  
### <a name="namespaces-and-type-name-conflicts"></a>Conflitti di nomi e spazi dei nomi  
 **X DO NOT** introducono i nomi di tipo generico, ad esempio `Element`, `Node`, `Log`, e `Message`.  
  
 È presente un'elevata probabilità che questa operazione porterà a digitare nome è in conflitto in comune scenari. È necessario qualificare i nomi di tipo generico (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).  
  
 Sono disponibili linee guida specifiche per evitare conflitti di nomi di tipo per le diverse categorie di spazi dei nomi.  
  
-   **Spazi dei nomi del modello di applicazione**  
  
     Gli spazi dei nomi che appartengono a un singolo modello di applicazione molto spesso vengono utilizzati insieme, ma non sono quasi mai usati con gli spazi dei nomi di altri modelli di applicazione. Ad esempio, il <xref:System.Windows.Forms?displayProperty=nameWithType> dello spazio dei nomi è molto raramente utilizzata in combinazione con il <xref:System.Web.UI?displayProperty=nameWithType> dello spazio dei nomi. Di seguito è riportato un elenco noto modello dello spazio dei nomi di gruppi di applicazioni:  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X DO NOT** assegnare lo stesso nome per i tipi negli spazi dei nomi all'interno di un modello di applicazione singolo.  
  
     Ad esempio, non aggiungere un tipo denominato `Page` per il <xref:System.Web.UI.Adapters?displayProperty=nameWithType> dello spazio dei nomi, perché le <xref:System.Web.UI?displayProperty=nameWithType> dello spazio dei nomi contiene già un tipo denominato `Page`.  
  
-   **Spazi dei nomi dell'infrastruttura**  
  
     Questo gruppo contiene spazi dei nomi che raramente vengono importati durante lo sviluppo di applicazioni comuni. Ad esempio, `.Design` gli spazi dei nomi sono utilizzati principalmente per strumenti di sviluppo di programmazione. Come evitare conflitti con i tipi in questi spazi dei nomi non è critico.  
  
-   **Spazi dei nomi core**  
  
     Gli spazi dei nomi core includono tutti `System` spazi dei nomi, esclusi gli spazi dei nomi dei modelli di applicazione e gli spazi dei nomi dell'infrastruttura. Spazi dei nomi core includono, ad esempio, `System`, `System.IO`, `System.Xml`, e `System.Net`.  
  
     **X DO NOT** consentono di tipi di nomi in conflitto con qualsiasi tipo negli spazi dei nomi dei componenti di base.  
  
     Ad esempio, non utilizzare mai `Stream` come nome di tipo. Genererebbe un conflitto con <xref:System.IO.Stream?displayProperty=nameWithType>, un molto usati tipo.  
  
-   **Gruppi dello spazio dei nomi di tecnologia**  
  
     Questa categoria include tutti gli spazi dei nomi con i primi due nodi dello spazio dei nomi stesso `(<Company>.<Technology>*`), ad esempio `Microsoft.Build.Utilities` e `Microsoft.Build.Tasks`. È importante che i tipi che appartengono a una sola tecnologia non sia in conflitto tra loro.  
  
     **X DO NOT** assegnare nomi dei tipi che possano entrare in conflitto con altri tipi all'interno di una singola tecnologia.  
  
     **X DO NOT** introdurre conflitti di nomi tra i tipi negli spazi dei nomi di tecnologia e uno spazio dei nomi del modello di applicazione (a meno che la tecnologia non deve essere utilizzato con il modello di applicazione).  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
