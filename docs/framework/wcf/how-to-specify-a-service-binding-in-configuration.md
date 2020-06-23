---
title: "Procedura: specificare un'associazione al servizio in configurazione"
description: Informazioni su come configurare un endpoint per un servizio WCF in un file di configurazione. Un contratto viene definito per un servizio e implementato in una classe.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
ms.openlocfilehash: 92d0834091a1f243df6be214f606fbf0093dca54
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244556"
---
# <a name="how-to-specify-a-service-binding-in-configuration"></a>Procedura: specificare un'associazione al servizio in configurazione
In questo esempio viene definito un contratto `ICalculator` per un servizio calcolatrice di base, il servizio viene implementato nella classe `CalculatorService`, quindi l'endpoint relativo viene configurato nel file Web.config dove viene specificato che il servizio utilizza <xref:System.ServiceModel.BasicHttpBinding>. Per una descrizione di come configurare questo servizio usando codice anziché una configurazione, vedere [procedura: specificare un'associazione al servizio nel codice](how-to-specify-a-service-binding-in-code.md).  
  
 La procedura solitamente consigliata consiste nello specificare in modo dichiarativo l'associazione e le informazioni dell'indirizzo nella configurazione anziché in modo imperativo nel codice. In genere definire endpoint nel codice non è pratico in quanto le associazioni e gli indirizzi di un servizio distribuito sono solitamente diversi da quelli usati durante lo sviluppo del servizio. Più in generale, se le informazioni su associazione e indirizzo non vengono incluse nel codice, tali dati possono essere modificati senza dover compilare o distribuire nuovamente l'applicazione.  
  
 È possibile eseguire tutti i passaggi di configurazione seguenti utilizzando lo [strumento Editor di configurazione (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Per la copia di origine di questo esempio, vedere l'oggetto di [base](./samples/basicbinding.md).  
  
## <a name="to-specify-the-basichttpbinding-to-use-to-configure-the-service"></a>Per specificare l'elemento BasicHttpBinding necessario per la configurazione del servizio  
  
1. Definire un contratto di servizio per il tipo di servizio.  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2. Implementare il contratto di servizio in una classe del servizio.  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    > L'indirizzo o le informazioni di associazione non sono specificate nell'implementazione del servizio. Non è necessario, inoltre, scrivere codice per recuperare le informazioni dal file di configurazione.  
  
3. Creare un file Web.config per configurare un endpoint per l'elemento  `CalculatorService` che utilizza la classe <xref:System.ServiceModel.WSHttpBinding>.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  

            <!-- Leave the address blank to be populated by default -->
            <!-- from the hosting environment,in this case IIS, so -->
            <!-- the address will just be that of the IIS Virtual -->
            <!-- Directory. -->

            <!-- Specify the binding configuration name for that -->
            <!-- binding type. This is optional but useful if you -->
            <!-- want to modify the properties of the binding. -->
            <!-- The bindingConfiguration name Binding1 is defined -->
            <!-- below in the bindings element. -->
            <endpoint
                address=""
                binding="wsHttpBinding"  
                bindingConfiguration="Binding1"  
                contract="ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <wsHttpBinding>  
            <binding name="Binding1">  
              <!-- Binding property values can be modified here. -->  
              <!-- See the next procedure. -->  
            </binding>  
          </wsHttpBinding>  
       </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. Creare un file Service.svc contenente la riga seguente e salvarlo nella directory virtuale di Internet Information Services (IIS).  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>
    ```  
  
## <a name="to-modify-the-default-values-of-the-binding-properties"></a>Per modificare i valori predefiniti delle proprietà dell'associazione  
  
1. Per modificare uno dei valori di proprietà predefiniti di <xref:System.ServiceModel.WSHttpBinding> , creare un nuovo nome di configurazione dell'associazione, `<binding name="Binding1">` all'interno dell' [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento e impostare i nuovi valori per gli attributi dell'associazione in questo elemento di associazione. Per impostare, ad esempio valori di timeout di apertura e chiusura predefiniti di 1-2 minuti, aggiungere quanto segue nel file di configurazione.  
  
    ```xml  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Uso di associazioni per configurare servizi e client](using-bindings-to-configure-services-and-clients.md)
- [Specifica di un indirizzo dell'endpoint](specifying-an-endpoint-address.md)
