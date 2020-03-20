---
title: 'Mitigazione: deserializzazione di oggetti tra domini app'
ms.date: 03/30/2017
ms.assetid: 30c2d66c-04a8-41a5-ad31-646b937f61b5
ms.openlocfilehash: e2d90a77cab699646bd31eaa162d1bd1744fd51b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457930"
---
# <a name="mitigation-deserialization-of-objects-across-app-domains"></a>Mitigazione: deserializzazione di oggetti tra domini app
In alcuni casi, quando in un'applicazione vengono utilizzati due o più domini applicazione con diverse basi di applicazione, il tentativo di deserializzare gli oggetti nel contesto di chiamata logico dei domini applicazione comporta la generazione di un'eccezione.  
  
## <a name="diagnosing-the-issue"></a>Diagnostica del problema  
 Il problema si presenta con la sequenza di condizioni seguente:  
  
1. In un'applicazione vengono utilizzati due o più domini applicazione con basi di applicazione diverse.  
  
2. Alcuni tipi vengono aggiunti esplicitamente all'oggetto <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> chiamando un metodo come <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> o <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>. Questi tipi non vengono contrassegnati come serializzabili e non sono archiviati nella Global Assembly Cache.  
  
3. Successivamente, tramite il codice in esecuzione nel dominio applicazione non predefinito viene effettuato il tentativo di lettura di un valore da un file di configurazione o di utilizzo di XML per deserializzare un oggetto.  
  
4. Per leggere da un file di configurazione o deserializzare l'oggetto, tramite un oggetto <xref:System.Xml.XmlReader> viene effettuato il tentativo di accesso al sistema di configurazione.  
  
5. Se il sistema di configurazione non è già stato inizializzato, deve completare la relativa inizializzazione. Ciò significa, ad esempio, che tramite il runtime deve essere creato un percorso stabile per un sistema di configurazione nel modo seguente:  
  
    1. Vengono cercate le evidenze per il dominio applicazione non predefinito.  
  
    2. Viene effettuato il tentativo di calcolo dell'evidenza per il dominio applicazione non predefinito in base a quello predefinito.  
  
    3. La chiamata per ottenere l'evidenza per il dominio applicazione predefinito comporta una chiamata tra domini applicazione dal dominio applicazione non predefinito a quello predefinito.  
  
    4. Come parte del contratto di dominio applicazione in .NET Framework, anche il contenuto del contesto di chiamata logico deve essere sottoposto a marshalling attraverso i limiti del dominio applicazione.  
  
6. Poiché i tipi presenti nel contesto di chiamata logico non possono essere risolti nel dominio applicazione predefinito, viene generata un'eccezione.  
  
## <a name="mitigation"></a>Strategia di riduzione del rischio  
 Per risolvere questo problema, effettuare le operazioni seguenti:  
  
1. Individuare la chiamata a `get_Evidence` nello stack di chiamate quando viene generata l'eccezione. L'eccezione può essere una qualsiasi di un subset di eccezioni, incluse <xref:System.IO.FileNotFoundException> e <xref:System.Runtime.Serialization.SerializationException>.  
  
2. Identificare la posizione nell'applicazione in cui nessun oggetto viene aggiunto al contesto di chiamata logico e aggiungere il codice seguente:  
  
    ```csharp
    System.Configuration.ConfigurationManager.GetSection("system.xml/xmlReader");  
    ```
  
## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
