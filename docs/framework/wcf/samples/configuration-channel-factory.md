---
title: Configurazione di una channel factory
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 3d439fb17d676ce337207a726fb9e491cf0a0ab0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="configuration-channel-factory"></a>Configurazione di una channel factory
In questo esempio viene descritto l'utilizzo di <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> consente la gestione centrale della configurazione client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Può essere anche utile in scenari nei quali la configurazione viene selezionata o modificata dopo la fase di caricamento del dominio dell'applicazione.  
  
## <a name="demonstrates"></a>Dimostrazione  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene descritto come utilizzare <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> per aggiungere uno specifico file di configurazione a un'applicazione client, senza che sia necessario utilizzare il file di configurazione dell'applicazione predefinito.  
  
 L'esempio è costituito da due progetti. Il primo progetto è un servizio semplice in esecuzione per rispondere a messaggi provenienti dai client. Il secondo progetto è un'applicazione client che compila due oggetti <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> utilizzando un <xref:System.Configuration.ExeConfigurationFileMap> per il file di configurazione Test.config e li utilizza per comunicare con il servizio. Entrambi i client comunicano con il servizio utilizzando la configurazione specificata in Test.config.  
  
 Il codice seguente aggiunge un file di configurazione personalizzato a un'applicazione client.  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegi di amministratore.  
  
2.  Pulsante destro del mouse sulla soluzione ConfigurationChannelFactory (2 progetti), quindi selezionare **proprietà**.  
  
3.  In **proprietà comuni**selezionare **progetto di avvio**, quindi fare clic su **più progetti di avvio**.  
  
4.  Spostare il **servizio** all'inizio dell'elenco, il progetto con il **azione 'Start'** e quindi spostare il **Client** progetto dopo la **servizio**progetto, anche con il **azione 'Start'**, pertanto il **Client** progetto viene eseguito dopo il **servizio** progetto.  
  
5.  Fare clic su **OK**, quindi premere F5 o CTRL + F5 per eseguire l'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
