---
title: 'Procedura: configurare le impostazioni del servizio COM+'
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
ms.openlocfilehash: d14fd1434cb87dc62babeabb79cb780e568aacb7
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46699014"
---
# <a name="how-to-configure-com-service-settings"></a>Procedura: configurare le impostazioni del servizio COM+
Quando l'interfaccia di un'applicazione viene aggiunta o rimossa usando lo strumento di configurazione del servizio COM+, la configurazione del servizio Web viene aggiornata nel file di configurazione dell'applicazione. Nella modalità di hosting COM+, il file Application config viene inserito nella Directory radice dell'applicazione (%PROGRAMFILES%\ComPlus applicazioni\\{appid} è l'impostazione predefinita). In entrambe le modalità di hosting Web il file Web.config è posizionato nella directory vroot specificata.  
  
> [!NOTE]
>  Per evitare la manomissione dei messaggi tra un client e un server è necessario firmare i messaggi. Inoltre, per evitare la diffusione di informazioni dai messaggi scambiati tra un client e un server è necessario usare la crittografia a livello di messaggio o di trasporto. Come per i servizi Windows Communication Foundation (WCF), è consigliabile usare la limitazione delle richieste per limitare il numero di chiamate simultanee, le connessioni, istanze e operazioni in sospeso. Ciò consente di evitare un utilizzo eccessivo di risorse. Il comportamento della limitazione delle richieste viene specificato tramite impostazioni del file di configurazione del servizio.  
  
## <a name="example"></a>Esempio  
 Si consideri un componente che implementa l'interfaccia seguente:  
  
```  
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 Se il componente viene esposto come un servizio Web, il contratto di servizio corrispondente che viene esposto, e al quale si devono conformare i client, è il seguente:  
  
```  
[ServiceContract(Session = true,  
Namespace = "http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7",  
Name = "IFinances")]  
public interface IFinancesContract : IDisposable  
{  
    [OperationContract]  
    string Debit(string accountNo, double amount);  
    [OperationContract]  
    string Credit(string accountNo, double amount);  
}  
```  
  
> [!NOTE]
>  L'IID fa parte dello spazio dei nomi iniziale per il contratto.  
  
 Le applicazioni client che usano questo servizio dovrebbero essere conformi a questo contratto, nonché usare un'associazione che sia compatibile con quella specificata nella configurazione dell'applicazione.  
  
 Nell'esempio di codice seguente viene illustrato un file di configurazione predefinito. Essendo un servizio Web di Windows Communication Foundation (WCF), ciò è conforme allo schema di configurazione del modello di servizio standard e può essere modificata nella esattamente come altri file di configurazione di servizi WCF.  
  
 Modifiche tipiche includono:  
  
- Modifica dell'indirizzo endpoint dal modulo ApplicationName/ComponentName/InterfaceName predefinito in un modulo maggiormente utilizzabile.  
  
- Modifica lo spazio dei nomi del servizio da quello predefinito `http://tempuri.org/InterfaceID` form da un modulo più attinente.  
  
- Modifica dell'endpoint per l'uso di un'associazione del trasporto differente.  
  
     Nel caso di un servizio COM+ ospitato, per impostazione predefinita viene usato il trasporto tramite named pipe. È comunque possibile usare un trasporto esterno al computer come TCP.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="comNonTransactionalBinding" />  
                <binding name="comTransactionalBinding" transactionFlow="true" />  
            </netNamedPipeBinding>  
        </bindings>  
        <comContracts>  
            <comContract contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"  
                name="IFinances" namespace="http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7"  
                requiresSession="true">  
                <exposedMethods>  
                    <add exposedMethod="Debit" />  
                    <add exposedMethod="Credit" />  
                </exposedMethods>  
            </comContract>  
        </comContracts>  
        <services>  
            <service name="{DCDB24CC-0B19-4534-95CD-FBBFF4D67DD9},{C942B840-AD54-4A44-B5F7-928130980AB9}">  
                <endpoint address="IFinances" binding="netNamedPipeBinding" bindingConfiguration="comNonTransactionalBinding"  
                    contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" />  
                <host>  
                    <baseAddresses>  
                        <add baseAddress="net.pipe://localhost/ServiceModelDocSampleApp/ServiceModelDocSample.esFinance" />  
                    </baseAddresses>  
                </host>  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Integrazione con applicazioni COM+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
