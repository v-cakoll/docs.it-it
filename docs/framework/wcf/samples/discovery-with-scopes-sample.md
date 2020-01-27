---
title: Esempio relativo all'individuazione di ambiti
ms.date: 03/30/2017
ms.assetid: 6a37a754-6b8c-4ebe-bdf2-d4f0520271d5
ms.openlocfilehash: 8ba5618f472fc8a6e1751776060f99103a67a073
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728747"
---
# <a name="discovery-with-scopes-sample"></a>Esempio relativo all'individuazione di ambiti

In questo esempio viene illustrato come utilizzare gli ambiti per suddividere in categorie gli endpoint individuabili e come utilizzare <xref:System.ServiceModel.Discovery.DiscoveryClient> per eseguire una ricerca asincrona per gli endpoint. Nel servizio questo esempio mostra come personalizzare l'individuazione per ogni endpoint aggiungendo un comportamento di individuazione dell'endpoint e utilizzandolo per aggiungere un ambito all'endpoint. Viene inoltre illustrato come controllare l'individuabilità dell'endpoint. Nel client l'esempio illustra come i client possono creare un <xref:System.ServiceModel.Discovery.DiscoveryClient> e ottimizzare i parametri di ricerca per includere gli ambiti aggiungendo ambiti a <xref:System.ServiceModel.Discovery.FindCriteria>. Questo esempio mostra anche come i client possono limitare le risposte aggiungendo un criterio di chiusura.

## <a name="service-features"></a>Funzionalità del servizio

Questo progetto mostra due endpoint del servizio aggiunti a un <xref:System.ServiceModel.ServiceHost>. Ogni endpoint dispone di un comportamento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> ad esso associato. Tale comportamento viene utilizzato per aggiungere ambiti URI per entrambi gli endpoint. Gli ambiti vengono utilizzati per distinguere ciascuno degli endpoint in modo che i client siano in grado di ottimizzare la ricerca. Per il secondo endpoint, l'individuabilità può essere disabilitata impostando la proprietà <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> su `false`. Ciò garantisce che i metadati di individuazione associati all'endpoint non siano inviati come parte di un messaggio di individuazione.

## <a name="client-features"></a>Funzionalità del client

Il metodo `FindCalculatorServiceAddress()` mostra come utilizzare un <xref:System.ServiceModel.Discovery.DiscoveryClient> e passare un <xref:System.ServiceModel.Discovery.FindCriteria> con due restrizioni. Un ambito viene aggiunto ai criteri e la proprietà <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> viene impostata su 1. L'ambito limita i risultati ai soli servizi che pubblicano lo stesso ambito. L'impostazione di <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> su 1 limita le risposte attese da <xref:System.ServiceModel.Discovery.DiscoveryClient> al massimo a 1 endpoint. La chiamata <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> è un'operazione sincrona che blocca il thread fino a quando non viene raggiunto un timeout o non viene individuato un endpoint.

### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Questo esempio usa endpoint HTTP e per eseguirlo è necessario aggiungere elenchi di controllo di accesso (ACL) agli URL appropriati. Per ulteriori informazioni, vedere [configurazione di http e HTTPS](../feature-details/configuring-http-and-https.md). L'esecuzione del comando seguente con privilegi elevati consente di aggiungere gli elenchi di controllo di accesso appropriati. È necessario sostituire dominio e nome utente per gli argomenti seguenti se il comando non funziona in modo corretto: `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. Compila la soluzione.

3. Eseguire il servizio eseguibile dalla directory di compilazione.

4. Eseguire il file eseguibile del client. Il client è in grado di individuare il servizio.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryWithScopes`
