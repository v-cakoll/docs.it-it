---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: cd4c4cd4c1bfe7920c438eddc15aba00d995b8cb
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039613"
---
# <a name="bindings"></a>associazioni di \<

È possibile utilizzare l'elemento `bindings` per configurare una raccolta di associazioni standard e personalizzate per Windows Communication Foundation (WCF). Ogni voce è un elemento `binding` che può essere identificato dal relativo `name` univoco. I servizi usano le associazioni collegandole mediante l'oggetto `name`. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).

## <a name="system-provided-bindings"></a>Associazioni fornite dal sistema

Le associazioni fornite dal sistema nascondono la complessità dello stack di messaggistica WCF. Le applicazioni che usano associazioni fornite dal sistema non richiedono il controllo completo sullo stack. Gli attributi esposti in ciascuna associazione fornita dal sistema sono quelli più appropriati per lo scenario di utilizzo gestito dall'associazione.

La sezione di configurazione di ciascuna associazione fornita dal sistema può definire varie configurazioni usate per configurare l'associazione. Ogni configurazione è identificata da un nome univoco.

Non è possibile aggiungere elementi o attributi a un'associazione fornita dal sistema. A tale scopo, è necessario implementare un'associazione personalizzata come descritto nella sezione [associazioni personalizzate](#custom-bindings) . È possibile definire un'associazione personalizzata che simula perfettamente un'associazione fornita dal sistema e aggiunge alcune impostazioni che l'applicazione utente vuole avere il controllo.  

Per un elenco delle associazioni fornite dal sistema, vedere [associazioni fornite dal sistema](../../../wcf/system-provided-bindings.md).

## <a name="custom-bindings"></a>Associazioni personalizzate

Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF. Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack. Ogni elemento definisce e configura un elemento dello stack. In ogni associazione personalizzata deve essere presente un solo elemento `transport`. Senza questo elemento, lo stack dei messaggi è incompleto.

L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio. L'ordine necessario per gli elementi dello stack è il seguente:  

1. Transazioni (facoltativo)  

2. Messaggistica affidabile (facoltativo)  

3. Sicurezza (facoltativo)  

4. Codificatore  

5. Trasporto  

 Le associazioni personalizzate sono identificate dal relativo attributo `name`. Per ulteriori informazioni sulle associazioni personalizzate, vedere [associazioni personalizzate](../../../wcf/extending/custom-bindings.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>
- [Associazioni](../../../wcf/bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<CustomBinding >](custombinding.md)
