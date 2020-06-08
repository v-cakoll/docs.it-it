---
title: Gestione delle connessioni
description: Informazioni sul modo in cui le applicazioni che usano HTTP per le risorse di dati possono usare le classi .NET Framework ServicePoint e ServicePointManager per gestire le connessioni.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, connections
- HTTP, classes for connecting
- requesting data from Internet, connections
- sending data, connections
- receiving data, connections
- ServicePoint class, about ServicePoint class
- response to Internet request, connections
- connections [.NET Framework], classes
- network resources, connections
- downloading Internet resources, connections
- ServicePointManager class, about ServicePointManager class
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
ms.openlocfilehash: 124dff1b104e323b929d13f73cf17d740e747c32
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502288"
---
# <a name="managing-connections"></a>Gestione delle connessioni
Le applicazioni che usano HTTP per connettersi alle risorse di dati possono usare le classi <xref:System.Net.ServicePoint> e <xref:System.Net.ServicePointManager> di .NET Framework per gestire le connessioni a Internet e ottenere prestazioni e scalabilità ottimali.  
  
 La classe **ServicePoint** offre un endpoint a cui un'applicazione può connettersi per accedere alle risorse Internet. Ogni **ServicePoint** contiene informazioni che consentono di ottimizzare le connessioni con un server Internet tramite la condivisione di informazioni sull'ottimizzazione tra le connessioni per migliorare le prestazioni.  
  
 Ogni **ServicePoint** è identificato da un URI (Uniform Resource Identifier) e viene categorizzato in base ai frammenti dell'URI che indicano host e identificatore di schema. Ad esempio, la stessa istanza di **ServicePoint** fornirà le richieste agli URI `http://www.contoso.com/index.htm` e `http://www.contoso.com/news.htm?date=today` perché hanno gli stessi frammenti per l'identificatore di schema (http) e l'host (`www.contoso.com`). Se l'applicazione dispone già di una connessione permanente al server `www.contoso.com`, userà tale connessione per recuperare entrambe le richieste, evitando la necessità di creare due connessioni.  
  
 **ServicePointManager** è una classe statica che gestisce la creazione e distruzione delle istanze di **ServicePoint**. **ServicePointManager** crea un **ServicePoint** quando l'applicazione richiede una risorsa Internet che non è presente nella raccolta di istanze di **ServicePoint** esistenti. Le istanze di **ServicePoint** vengono eliminate definitivamente quando superano il tempo di inattività massimo o quando il numero di istanze di **ServicePoint** esistenti supera il numero massimo di istanze di **ServicePoint** per l'applicazione. È possibile controllare sia il tempo di inattività massimo predefinito che il numero massimo di istanze di **ServicePoint** impostando le proprietà <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> e <xref:System.Net.ServicePointManager.MaxServicePoints%2A> in **ServicePointManager**.  
  
 Il numero di connessioni tra un client e un server può avere un impatto significativo sulla velocità effettiva dell'applicazione. Per impostazione predefinita, un'applicazione che usa la classe <xref:System.Net.HttpWebRequest> usa al massimo due connessioni permanenti a un determinato server, ma è possibile impostare il numero massimo di connessioni per ogni singola applicazione.  
  
> [!NOTE]
> La specifica HTTP/1.1 limita il numero di connessioni da un'applicazione a due connessioni per server.  
  
 Il numero ottimale di connessioni dipende dalle condizioni effettive di esecuzione dell'applicazione. L'aumento del numero di connessioni disponibili per l'applicazione potrebbe non influire sulle prestazioni dell'applicazione. Per determinare l'impatto dell'aggiunta di altre connessioni, eseguire più test delle prestazioni variando il numero di connessioni. È possibile modificare il numero di connessioni usate da un'applicazione modificando la proprietà <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> statica nella classe **ServicePointManager** durante l'inizializzazione dell'applicazione, come illustrato nell'esempio di codice seguente.  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 La modifica della proprietà **ServicePointManager.DefaultConnectionLimit** non influisce sulle istanze di **ServicePoint** inizializzate in precedenza. Il codice seguente illustra la modifica del limite di connessione per un'istanza esistente di **ServicePoint** per il server `http://www.contoso.com` sul valore archiviato in `newLimit`.  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## <a name="see-also"></a>Vedere anche

- [Raggruppamento delle connessioni](connection-grouping.md)
- [Uso di protocolli applicativi](using-application-protocols.md)
