---
title: 'Procedura: usare il moniker servizio di Windows Communication Foundation senza registrazione'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: f69314948a0e0a69e49ec148f94572f17d0b8e3c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595050"
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a>Procedura: usare il moniker servizio di Windows Communication Foundation senza registrazione
Per connettersi a e comunicare con un servizio Windows Communication Foundation (WCF), un'applicazione client WCF deve disporre dei dettagli relativi all'indirizzo del servizio, alla configurazione dell'associazione e al contratto di servizio.  
  
 Il moniker del servizio WCF ottiene in genere il contratto richiesto tramite la registrazione precedente dei tipi di attributo richiesti, ma in alcuni casi non è fattibile. Invece che con la registrazione, il moniker può ottenere la definizione del contratto nella forma di un documento WSDL (Web Services Definition Language) tramite l'uso del parametro `wsdl` o dello scambio metadati, tramite il parametro `mexAddress`.  
  
 Questo consente scenari quali la distribuzione di un foglio di calcolo Excel in cui alcuni dei valori delle celle sono calcolati tramite interazioni di servizi Web. In questo scenario, potrebbe non essere fattibile registrare l'assembly del contratto di servizio su tutti i client che potrebbero aprire il documento. Il parametro `wsdl` o `mexAddress` consente una soluzione autonoma.  
  
> [!NOTE]
> È necessario usare l'autenticazione reciproca per proteggersi dalla manomissione o lo spoofing di richieste e risposte. In particolare, è importante per i client assicurarsi che l'endpoint di scambio metadati che sta rispondendo sia la parte attendibile prevista.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato l'uso del moniker servizio con un contratto MEX. Un servizio con il contratto seguente viene esposto con un wsHttpBinding.  
  
```csharp
using System.ServiceModel;  
  
// ...
  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Demo")]  
public interface IAffiliate  
{  
    [OperationContract]  
    bool NewAffiliate(string ID, string company, string fullname, string accountsCode);  
    [OperationContract]  
    bool RemoveAffiliate(string ID);  
    [OperationContract]  
    double RevenueCheckMonthly(ref string ID);  
    [OperationContract]  
    double RevenueCheckTotal(ref string ID);  
}  
```  
  
 Per costruire un client WCF per il servizio remoto, è possibile usare la stringa del moniker di esempio seguente.  
  
```
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 Durante l'esecuzione dell'applicazione client, il client esegue un `WS-MetadataExchange` con l'elemento `mexAddress` fornito. Questa operazione potrebbe restituire dettagli sull'indirizzo, l'associazione e il contratto per diversi servizi. I parametri `address`, `contract`, `contractNamespace`, `binding` e `bindingNamespace` vengono usati per identificare il servizio designato. Una volta che tali parametri sono stati confrontati, il moniker costruisce un client WCF con la definizione del contratto appropriata e le chiamate possono essere eseguite utilizzando il client WCF, come nel contratto tipizzato.  
  
> [!NOTE]
> Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida. Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: registrare e configurare un moniker servizio](how-to-register-and-configure-a-service-moniker.md)
