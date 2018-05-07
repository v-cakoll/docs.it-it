---
title: 'Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 6265860c2e1efb2f74a0243157a223a33889629a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati
Dopo aver sviluppato alcuni nuovi servizi WCF, si potrebbe decidere che si desidera essere in grado di chiamare questi servizi da uno script o un'applicazione Visual Basic 6.0. Un metodo, è possibile generare un assembly client WCF, registrare l'assembly con COM, installare l'assembly nella Global Assembly Cache e quindi fare riferimento ai tipi COM dal codice Visual Basic. Quando si distribuisce l'applicazione, è necessario distribuire anche l'assembly Client WCF. L'utente dovrà quindi registrare l'assembly client WCF con COM e posizionarlo nella cache di assembly globale. Interoperabilità COM WCF consente inoltre di apportare le stesse chiamate al servizio senza basarsi su un assembly client WCF. Il moniker WCF consente di chiamare qualsiasi servizio WCF da qualsiasi linguaggio compatibile con COM (Visual Basic, VBScript, Visual Basic, Applications Edition (VBA) e così via) specificando un endpoint di exchange (Mex) metadati URI che utilizza il moniker del servizio per estrarre tipo informazioni sul servizio. In questo argomento viene descritto come chiamare l'esempio di recupero WCF usando un moniker WCF che specifica un endpoint Mex.  
  
> [!NOTE]
>  I tipi definiti dall'assembly client WCF sono mai creata un'istanza. e l'assembly viene usato solo per i metadati.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Utilizzo del moniker del servizio con un indirizzo Mex  
  
1.  Compilare l'esempio di Guida introduttiva e usare Internet Explorer per passare all'URL (http://localhost/ServiceModelSamples/Service.svc) per verificare che il servizio sia in funzione.  
  
2.  Creare uno script di Visual Basic o un'applicazione Visual Basic che contiene il codice seguente:  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  Eseguire l'applicazione o lo script Visual Basic.  
  
    > [!NOTE]
    >  Il servizio che si sta chiamando deve esporre un endpoint Mex affinché il moniker sia in grado di leggere i metadati dal servizio. Per ulteriori informazioni, vedere [procedura: pubblicare metadati per un servizio utilizzando un File di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
    > [!NOTE]
    >  Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida.  Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Usare il moniker servizio di Windows Communication Foundation senza registrazione](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [Procedura: usare un moniker servizio con contratti WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
