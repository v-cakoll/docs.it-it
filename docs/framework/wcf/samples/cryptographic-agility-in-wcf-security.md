---
title: Agilità di crittografia nella sicurezza WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: a97f0b908d3c4d2e14fb55ec21371322dc740e47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668899"
---
# <a name="cryptographic-agility-in-wcf-security"></a>Agilità di crittografia nella sicurezza WCF
In questo esempio viene illustrato come specificare un algoritmo standard/personalizzato per fornire un'implementazione di crittografia agile in un servizio e client Windows Communication Foundation (WCF). L'esempio è costituito dai progetti seguenti:

 Servizio che si tratta di un servizio WCF self-hosted che implementa il `ICalculator` l'interfaccia e protegge l'endpoint usando il <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> con sessione protetta e sessione affidabile disabilitate. Il servizio definisce una classe `SecurityAlgorithmSuite` personalizzata per specificare gli algoritmi di crittografia da usare per la sicurezza dei messaggi.

 Client si tratta di un WCFclient che accede al servizio al termine dell'autenticazione. Richiama le operazioni esposte dall'interfaccia `ICalculator` e viene implementa dal servizio. Il servizio definisce inoltre la stessa classe `SecurityAlgorithmSuite` personalizzata per specificare gli algoritmi di crittografia da usare per la sicurezza dei messaggi.

### <a name="to-use-this-sample"></a>Per usare questo esempio

1.  Aprire la soluzione Cryptoagility in Visual Studio 2012.

2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.

3.  Aprire [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] e passare alla directory \WCF\Basic\Security\CryptoAgility\Service\bin ed eseguire il file service.exe con privilegi di amministratore facendo clic service.exe e selezionando **Esegui come amministratore**.

4.  Passare alla directory \WCF\Basic\Security\CryptoAgility\Client\bin ed eseguire il file client.exe.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a>Vedere anche
- [Sicurezza](../../../../docs/framework/wcf/feature-details/security.md)
