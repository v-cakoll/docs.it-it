---
title: Configurazione di una channel factory
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 0f00ba5e217420fe416100071d380e413c3df118
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183955"
---
# <a name="configuration-channel-factory"></a>Configurazione di una channel factory
In questo esempio viene descritto l'utilizzo di <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. Il <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> consente la gestione centralizzata della configurazione del client WCF. Può essere anche utile in scenari nei quali la configurazione viene selezionata o modificata dopo la fase di caricamento del dominio dell'applicazione.

## <a name="demonstrates"></a>Dimostra
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a>Discussione
 In questo esempio viene descritto come utilizzare <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> per aggiungere uno specifico file di configurazione a un'applicazione client, senza che sia necessario utilizzare il file di configurazione dell'applicazione predefinito.

 L'esempio è costituito da due progetti. Il primo progetto è un servizio semplice in esecuzione per rispondere a messaggi provenienti dai client. Il secondo progetto è un'applicazione client che compila due oggetti <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> utilizzando un <xref:System.Configuration.ExeConfigurationFileMap> per il file di configurazione Test.config e li utilizza per comunicare con il servizio. Entrambi i client comunicano con il servizio utilizzando la configurazione specificata in Test.config.

 Il codice seguente aggiunge un file di configurazione personalizzato a un'applicazione client.

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Aprire Visual Studio 2012 con privilegi di amministratore.

2. Fare clic con il pulsante destro del mouse sulla soluzione ConfigurationChannelFactory (2 progetti) e quindi **scegliere Proprietà**.

3. In **Proprietà comuni**selezionare Progetto di **avvio**e quindi fare clic su **Progetti di avvio multipli**.

4. Spostare il progetto **di** servizio all'inizio dell'elenco, con **l'azione 'Avvia',** quindi spostare il progetto **Client** dopo il progetto **di servizio,** anche con **l'azione 'Avvia',** in modo che il progetto **Client** venga eseguito dopo il progetto **di servizio.**

5. Fare clic **su OK**, quindi premere F5 (o CTRL-F5) per eseguire l'esempio.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
