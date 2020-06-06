---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: fe8f620668e35183890b8bba1f254a74c962f8d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139670"
---
# \<bindings>

È possibile utilizzare l' `bindings` elemento per configurare una raccolta di associazioni standard e personalizzate per Windows Communication Foundation (WCF). Ogni voce è un elemento `binding` che può essere identificato dal relativo `name` univoco. I servizi usano le associazioni collegandole mediante l'oggetto `name`. A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome. Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).

## <a name="system-provided-bindings"></a>Associazioni fornite dal sistema

Le associazioni fornite dal sistema nascondono la complessità dello stack di messaggistica WCF. Le applicazioni che usano associazioni fornite dal sistema non richiedono il controllo completo sullo stack. Gli attributi esposti in ciascuna associazione fornita dal sistema sono quelli più appropriati per lo scenario di utilizzo gestito dall'associazione.

La sezione di configurazione di ciascuna associazione fornita dal sistema può definire varie configurazioni usate per configurare l'associazione. Ogni configurazione è identificata da un nome univoco.

Non è possibile aggiungere elementi o attributi a un'associazione fornita dal sistema. A tale scopo, è necessario implementare un'associazione personalizzata come descritto nella sezione [associazioni personalizzate](#custom-bindings) . È possibile definire un'associazione personalizzata che simula perfettamente un'associazione fornita dal sistema e aggiunge alcune impostazioni che l'applicazione utente vuole avere il controllo.  

Per un elenco delle associazioni fornite dal sistema, vedere [associazioni fornite dal sistema](../../../wcf/system-provided-bindings.md).

## <a name="custom-bindings"></a>Binding personalizzati

Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF. Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack. Ogni elemento definisce e configura un elemento dello stack. In ogni associazione personalizzata deve essere presente un solo elemento `transport`. Senza questo elemento, lo stack dei messaggi è incompleto.

L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio. L'ordine necessario per gli elementi dello stack è il seguente:  

1. Transazioni (facoltativo)  

2. Messaggistica affidabile (facoltativo)  

3. Sicurezza (facoltativo)  

4. Codificatore  

5. Trasporto  

 Le associazioni personalizzate sono identificate dal relativo attributo `name`. Per ulteriori informazioni sulle associazioni personalizzate, vedere [associazioni personalizzate](../../../wcf/extending/custom-bindings.md).

## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>
- [Binding](../../../wcf/bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
