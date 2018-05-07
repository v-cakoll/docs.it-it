---
title: Configurazione dei comportamenti client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 062e726b6f1d6831303e1cc0ae82a434daab860c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-client-behaviors"></a>Configurazione dei comportamenti client
Windows Communication Foundation (WCF) consente di configurare i comportamenti in due modi: facendo riferimento alle configurazioni dei comportamenti sono definite nel `<behavior>` sezione di un file di configurazione dell'applicazione client- o a livello di chiamata applicazione. In questo argomento vengono illustrati entrambi gli approcci.  
  
 Quando di usa un file di configurazione, la configurazione del comportamento è una raccolta denominata di impostazioni di configurazione. Il nome di ogni configurazione di comportamento deve essere univoco. Questa stringa viene usata nell'attributo `behaviorConfiguration` di una configurazione endpoint per collegare l'endpoint al comportamento.  
  
## <a name="example"></a>Esempio  
 Nel codice di configurazione seguente viene definito un comportamento denominato `myBehavior`. L'endpoint client fa riferimento a questo comportamento nell'attributo `behaviorConfiguration`.  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-behaviors-programmatically"></a>Uso di comportamenti a livello di programmazione  
 È anche possibile configurare o inserire comportamenti a livello di programmazione individuando appropriata `Behaviors` proprietà per l'oggetto client di Windows Communication Foundation (WCF) o per l'oggetto factory di canale client prima dell'apertura del client.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come inserire un comportamento a livello di programmazione accedendo alla proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> nell'oggetto <xref:System.ServiceModel.Description.ServiceEndpoint> restituito dalla proprietà <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> prima della creazione dell'oggetto channel.  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a>Vedere anche  
 [\<i comportamenti >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
