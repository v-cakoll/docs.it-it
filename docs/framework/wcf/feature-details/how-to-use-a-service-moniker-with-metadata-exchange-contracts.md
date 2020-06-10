---
title: 'Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 04a940a6e8f010e5cd851684c5fc62bab2a1a034
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601166"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati
Dopo aver sviluppato alcuni nuovi servizi WCF, è possibile decidere di poter chiamare questi servizi da uno script o da un'applicazione Visual Basic 6,0. Un metodo consiste nel generare un assembly client WCF, registrare l'assembly con COM, installare l'assembly nella GAC, quindi fare riferimento ai tipi COM dal codice Visual Basic. Quando si distribuisce l'applicazione, sarà necessario distribuire anche l'assembly client WCF. L'utente dovrà quindi registrare l'assembly client WCF con COM e posizionarlo nella cache di assembly globale. L'interoperabilità COM di WCF consente inoltre di effettuare le stesse chiamate al servizio senza basarsi su un assembly client WCF. Il moniker WCF consente di chiamare qualsiasi servizio WCF da qualsiasi linguaggio compatibile con COM (Visual Basic, VBScript, Visual Basic, Applications Edition (VBA) e così via) specificando un URI dell'endpoint MEX (Metadata Exchange) che il moniker del servizio utilizza per estrarre le informazioni sul tipo relative al servizio. In questo argomento viene illustrato come chiamare l'esempio WCF Introduzione usando un moniker WCF che specifica un endpoint MEX.  
  
> [!NOTE]
> I tipi definiti dall'assembly client WCF non vengono mai creati in realtà. e l'assembly viene usato solo per i metadati.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Utilizzo del moniker del servizio con un indirizzo Mex  
  
1. Compilare l'esempio Introduzione e utilizzare Internet Explorer per passare all'URL ( `http://localhost/ServiceModelSamples/Service.svc` ) per assicurarsi che il servizio sia funzionante.  
  
2. Creare uno script di Visual Basic o un'applicazione Visual Basic che contiene il codice seguente:  
  
    ```vb
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. Eseguire l'applicazione o lo script Visual Basic.  
  
    > [!NOTE]
    > Il servizio che si sta chiamando deve esporre un endpoint Mex affinché il moniker sia in grado di leggere i metadati dal servizio. Per altre informazioni, vedere [procedura: pubblicare metadati per un servizio usando un file di configurazione](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
    > [!NOTE]
    > Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida.  Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: usare il moniker servizio di Windows Communication Foundation senza registrazione](use-the-wcf-service-moniker-without-registration.md)
- [Procedura: usare un moniker di servizio con i contratti WSDL](how-to-use-a-service-moniker-with-wsdl-contracts.md)
