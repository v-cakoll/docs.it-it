---
title: <bindingExtensions>
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: 6eed4e8c549bccb06d8d425b084554a2ec7a1183
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272760"
---
# <a name="bindingextensions"></a><span data-ttu-id="979fb-101">\<bindingExtensions></span><span class="sxs-lookup"><span data-stu-id="979fb-101">\<bindingExtensions></span></span>
<span data-ttu-id="979fb-102">Questa sezione consente l'uso di un'associazione definita dall'utente dal file di configurazione di un computer o di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="979fb-102">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="979fb-103">È possibile aggiungere un binding definito dall'utente a questa raccolta usando la parola chiave `add` e impostando l'attributo `type` dell'elemento su un'associazione definita dall'utente e anche l'attributo `name` sul nome dell'associazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="979fb-103">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>  
  
 <span data-ttu-id="979fb-104">Le estensioni dell'associazione consentono di creare associazioni definite dall'utente da usare come parte di una configurazione di endpoint.</span><span class="sxs-lookup"><span data-stu-id="979fb-104">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="979fb-105">A livello di programmazione, un'estensione di associazione è un tipo che implementa la classe astratta <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="979fb-105">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>  
  
 <span data-ttu-id="979fb-106">Nell'esempio seguente viene usato l'elemento `add` e l'attributo `name` per aggiungere un'estensione di associazione alla sezione `bindingElementExtensions` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="979fb-106">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
      <add name="MyBinding"
           type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="979fb-107">Per aggiungere capacità di configurazione all'elemento, è necessario scrivere e registrare un elemento `bindingSection`.</span><span class="sxs-lookup"><span data-stu-id="979fb-107">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="979fb-108">Per altre informazioni a tal proposito, vedere la documentazione di <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="979fb-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="979fb-109">Dopo la definizione dell'elemento e del relativo tipo di configurazione, è possibile usare l'estensione in un endpoint come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="979fb-109">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example.</span></span>  
  
```xml  
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="979fb-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="979fb-110">See also</span></span>
- [<span data-ttu-id="979fb-111">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="979fb-111">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
