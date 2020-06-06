---
title: <bindingExtensions>
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: bd6aeb32e0994bceb9e56bcb1c6267f4cb64a5a4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73039149"
---
# \<bindingExtensions>

Questa sezione consente l'uso di un'associazione definita dall'utente dal file di configurazione di un computer o di un'applicazione. È possibile aggiungere un binding definito dall'utente a questa raccolta usando la parola chiave `add` e impostando l'attributo `type` dell'elemento su un'associazione definita dall'utente e anche l'attributo `name` sul nome dell'associazione definita dall'utente.

Le estensioni dell'associazione consentono di creare associazioni definite dall'utente da usare come parte di una configurazione di endpoint. A livello di programmazione, un'estensione di associazione è un tipo che implementa la classe astratta <xref:System.ServiceModel.Channels.Binding>.

Nell'esempio seguente viene usato l' `add` elemento e l' `name` attributo per aggiungere un'estensione di associazione alla `bindingExtensions` sezione del file di configurazione:

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

Per aggiungere capacità di configurazione all'elemento, è necessario scrivere e registrare un elemento `bindingSection`. Per altre informazioni a tal proposito, vedere la documentazione di <xref:System.Configuration>.

Dopo la definizione dell'elemento e del relativo tipo di configurazione, l'estensione può essere usata come parte di un endpoint, come illustrato nell'esempio seguente:

```xml
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```

## <a name="see-also"></a>Vedi anche

- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
