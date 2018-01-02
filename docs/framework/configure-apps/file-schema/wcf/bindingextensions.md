---
title: '&lt;bindingExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58392fc71508c3cf6ad7178396a927cf0e84c98f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltbindingextensionsgt"></a><span data-ttu-id="f6b0b-102">&lt;bindingExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="f6b0b-102">&lt;bindingExtensions&gt;</span></span>
<span data-ttu-id="f6b0b-103">Questa sezione consente l'uso di un'associazione definita dall'utente dal file di configurazione di un computer o di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f6b0b-103">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="f6b0b-104">È possibile aggiungere un binding definito dall'utente a questa raccolta usando la parola chiave `add` e impostando l'attributo `type` dell'elemento su un'associazione definita dall'utente e anche l'attributo `name` sul nome dell'associazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f6b0b-104">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>  
  
 <span data-ttu-id="f6b0b-105">Le estensioni dell'associazione consentono di creare associazioni definite dall'utente da usare come parte di una configurazione di endpoint.</span><span class="sxs-lookup"><span data-stu-id="f6b0b-105">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="f6b0b-106">A livello di programmazione, un'estensione di associazione è un tipo che implementa la classe astratta <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="f6b0b-106">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>  
  
 <span data-ttu-id="f6b0b-107">Nell'esempio seguente viene usato l'elemento `add` e l'attributo `name` per aggiungere un'estensione di associazione alla sezione `bindingElementExtensions` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f6b0b-107">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingExtensions>  
           <add name="MyBinding" type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="f6b0b-108">Per aggiungere capacità di configurazione all'elemento, è necessario scrivere e registrare un elemento `bindingSection`.</span><span class="sxs-lookup"><span data-stu-id="f6b0b-108">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="f6b0b-109">Per altre informazioni a tal proposito, vedere la documentazione di <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="f6b0b-109">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="f6b0b-110">Dopo la definizione dell'elemento e del relativo tipo di configurazione, è possibile usare l'estensione in un endpoint come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f6b0b-110">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example.</span></span>  
  
```xml  
<services>  
    <service name="MyService">  
        <endpoint address="myAddress" binding="MyBinding" />  
    </service>  
</services>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6b0b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6b0b-111">See Also</span></span>  
 [<span data-ttu-id="f6b0b-112">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="f6b0b-112">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
