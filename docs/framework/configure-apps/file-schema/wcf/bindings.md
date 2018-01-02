---
title: '&lt;associazioni&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d89fc465c1e82fab638b57dbf712f1396385f80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltbindingsgt"></a>&lt;associazioni&gt;
Questa sezione contiene una raccolta di associazioni standard e personalizzate. Ogni voce è un elemento `binding` che può essere identificato dal relativo `name` univoco. I servizi usano le associazioni collegandole mediante l'oggetto `name`. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="system-provided-binding"></a>Associazione fornita dal sistema  
 Le associazioni fornite dal sistema nascondono la complessità dello stack di messaggistica WCF. Le applicazioni che usano associazioni fornite dal sistema non richiedono il controllo completo sullo stack. Gli attributi esposti in ciascuna associazione fornita dal sistema sono quelli più appropriati per lo scenario di utilizzo gestito dall'associazione.  
  
 La sezione di configurazione di ciascuna associazione fornita dal sistema può definire varie configurazioni usate per configurare l'associazione. Ogni configurazione è identificata da un nome univoco.  
  
 Non è possibile aggiungere elementi o attributi a un'associazione fornita dal sistema. A tal scopo, è necessario implementare un'associazione personalizzata come descritto nella sezione "Associazione personalizzata" di questo argomento. È possibile definire un'associazione personalizzata che riproduce perfettamente un'associazione fornita dal sistema e aggiunge alcune impostazioni sulle quali è desiderabile che l'applicazione utente abbia il controllo.  
  
 Per un elenco di associazioni fornite dal sistema, vedere [associazioni fornite dal sistema](../../../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="custom-binding"></a>Associazione personalizzata  
 Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF. Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack. Ogni elemento definisce e configura un elemento dello stack. In ogni associazione personalizzata deve essere presente un solo elemento `transport`. Senza questo elemento, lo stack dei messaggi è incompleto.  
  
 L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio. L'ordine necessario per gli elementi dello stack è il seguente:  
  
1.  Transazioni (facoltativo)  
  
2.  Messaggistica affidabile (facoltativo)  
  
3.  Sicurezza (facoltativo)  
  
4.  Codificatore  
  
5.  Trasporto  
  
 Le associazioni personalizzate sono identificate dal relativo attributo `name`. Per ulteriori informazioni sulle associazioni personalizzate, vedere [associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [\<associazione >](../../../../../docs/framework/misc/binding.md)
