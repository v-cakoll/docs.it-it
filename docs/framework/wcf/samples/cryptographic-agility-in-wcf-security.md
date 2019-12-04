---
title: Agilità di crittografia nella sicurezza di WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: 2dbacd53876ded76ea212dd5656cd2dded4a6e48
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714930"
---
# <a name="cryptographic-agility-in-wcf-security"></a>Agilità di crittografia nella sicurezza di WCF

In questo esempio viene illustrato come specificare in un algoritmo standard o personalizzato per fornire un'implementazione di crittografia agile in un client e un servizio Windows Communication Foundation (WCF). L'esempio è costituito dai progetti seguenti:

**Service**

Si tratta di un servizio WCF self-hosted che implementa l'interfaccia `ICalculator` e protegge l'endpoint usando il <xref:System.ServiceModel.WSHttpBinding> con la sessione protetta e la sessione affidabile disabilitata. Il servizio definisce una classe `SecurityAlgorithmSuite` personalizzata per specificare gli algoritmi di crittografia da usare per la sicurezza dei messaggi.

**Client**

Si tratta di un client WCF che accede al servizio dopo il completamento dell'autenticazione. Richiama le operazioni esposte dall'interfaccia `ICalculator` e viene implementa dal servizio. Il servizio definisce inoltre la stessa classe `SecurityAlgorithmSuite` personalizzata per specificare gli algoritmi di crittografia da usare per la sicurezza dei messaggi.

## <a name="to-use-this-sample"></a>Per usare questo esempio

1. Aprire la soluzione soluzione CryptoAgility. sln in Visual Studio 2012.

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

3. Aprire Esplora file e passare alla directory \WCF\Basic\Security\CryptoAgility\Service\bin ed eseguire il file Service. exe con privilegi di amministratore facendo clic con il pulsante destro del mouse su Service. exe e scegliendo **Esegui come amministratore**.

4. Passare alla directory \WCF\Basic\Security\CryptoAgility\Client\bin ed eseguire il file client.exe.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a>Vedere anche

- [Sicurezza Windows Communication Foundation](../feature-details/security.md)
