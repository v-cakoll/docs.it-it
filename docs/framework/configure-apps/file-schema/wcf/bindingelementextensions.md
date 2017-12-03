---
title: '&lt;bindingElementExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71fdc7c68ff7e672a5adf044bbe0200563772a58
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltbindingelementextensionsgt"></a><span data-ttu-id="1dd1d-102">&lt;bindingElementExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="1dd1d-102">&lt;bindingElementExtensions&gt;</span></span>
<span data-ttu-id="1dd1d-103">Questa sezione consente l'uso di un elemento di associazione personalizzata dal file di configurazione di un computer o di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1dd1d-103">This section enables the use of a custom binding element from a machine or application configuration file.</span></span> <span data-ttu-id="1dd1d-104">È possibile aggiungere un elemento di associazione personalizzato a questa raccolta usando la parola chiave `add` e impostando l'attributo `type` dell'elemento su un'estensione dell'elemento di associazione, oltre all'attributo `name` sull'elemento di associazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1dd1d-104">You can add a custom binding element to this collection by using the `add` keyword, and setting the `type` attribute of the element to a binding element extension, as well as the `name` attribute to the custom binding element.</span></span>  
  
 <span data-ttu-id="1dd1d-105">Le estensioni delle associazioni consentono di creare elementi di associazione definiti dall'utente da usare come parti di associazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1dd1d-105">Binding extensions enable the user to create user-defined binding elements for use as part of custom bindings.</span></span> <span data-ttu-id="1dd1d-106">A livello di programmazione, un'estensione di associazione è un tipo che implementa la classe astratta <xref:System.ServiceModel.Channels.BindingElement>.</span><span class="sxs-lookup"><span data-stu-id="1dd1d-106">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.BindingElement>.</span></span> <span data-ttu-id="1dd1d-107">Nel file di configurazione, la sezione `bindingElementExtensions` è usata per definire un elemento dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="1dd1d-107">In the configuration file, the `bindingElementExtensions` section is used to define an extension element.</span></span>  
  
 <span data-ttu-id="1dd1d-108">Nell'esempio seguente viene usato l'elemento `add` e l'attributo `name` per aggiungere un'estensione di associazione alla sezione `bindingElementExtensions` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1dd1d-108">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="1dd1d-109">Per aggiungere capacità di configurazione all'elemento, è necessario scrivere e registrare un elemento `bindingElementExtensionSection`.</span><span class="sxs-lookup"><span data-stu-id="1dd1d-109">To add configuration abilities to the element, the user needs to write and register a `bindingElementExtensionSection` element.</span></span> <span data-ttu-id="1dd1d-110">Per altre informazioni a tal proposito, vedere la documentazione di <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="1dd1d-110">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="1dd1d-111">Dopo la definizione dell'elemento e del relativo tipo di configurazione, è possibile usare l'estensione in un'associazione personalizzata come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1dd1d-111">After the element and its configuration type are defined, the extension can be used as part of a custom binding as shown in the following example.</span></span>  
  
```xml  
<customBinding>  
     <binding name="test2">  
         <udpTransport />  
         <binaryMessageEncoding maxReadPoolSize="211" maxWritePoolSize="2132"  
             maxSessionSize="3141" />  
         </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1dd1d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dd1d-112">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>  
 [<span data-ttu-id="1dd1d-113">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="1dd1d-113">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
