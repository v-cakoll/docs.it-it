---
title: '&lt;bindingElementExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
ms.openlocfilehash: a93474a4f86fac2a6b211652e3ddc86901cf197f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltbindingelementextensionsgt"></a>&lt;bindingElementExtensions&gt;
Questa sezione consente l'uso di un elemento di associazione personalizzata dal file di configurazione di un computer o di un'applicazione. È possibile aggiungere un elemento di associazione personalizzato a questa raccolta usando la parola chiave `add` e impostando l'attributo `type` dell'elemento su un'estensione dell'elemento di associazione, oltre all'attributo `name` sull'elemento di associazione personalizzato.  
  
 Le estensioni delle associazioni consentono di creare elementi di associazione definiti dall'utente da usare come parti di associazioni personalizzate. A livello di programmazione, un'estensione di associazione è un tipo che implementa la classe astratta <xref:System.ServiceModel.Channels.BindingElement>. Nel file di configurazione, la sezione `bindingElementExtensions` è usata per definire un elemento dell'estensione.  
  
 Nell'esempio seguente viene usato l'elemento `add` e l'attributo `name` per aggiungere un'estensione di associazione alla sezione `bindingElementExtensions` del file di configurazione.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingElementExtensions>  
           <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingElementExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 Per aggiungere capacità di configurazione all'elemento, è necessario scrivere e registrare un elemento `bindingElementExtensionSection`. Per altre informazioni a tal proposito, vedere la documentazione di <xref:System.Configuration>.  
  
 Dopo la definizione dell'elemento e del relativo tipo di configurazione, è possibile usare l'estensione in un'associazione personalizzata come illustrato nell'esempio seguente.  
  
```xml  
<customBinding>  
     <binding name="test2">  
         <udpTransport />  
         <binaryMessageEncoding maxReadPoolSize="211" maxWritePoolSize="2132"  
             maxSessionSize="3141" />  
         </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>  
 [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)
