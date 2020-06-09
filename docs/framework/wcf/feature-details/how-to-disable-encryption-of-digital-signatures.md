---
title: 'Procedura: disattivare la crittografia delle firme digitali'
ms.date: 03/30/2017
ms.assetid: fd174313-ad81-4dca-898a-016ccaff8187
ms.openlocfilehash: 7ef305fdfd9a4ee61dfd89fdd46f2dc03a350977
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595401"
---
# <a name="how-to-disable-encryption-of-digital-signatures"></a>Procedura: disattivare la crittografia delle firme digitali
Per impostazione predefinita, un messaggio viene firmato e la firma viene crittografata digitalmente. Per controllare questo comportamento è necessario creare un'associazione personalizzata con un'istanza della classe <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> e impostare la proprietà `MessageProtectionOrder` della classe su un valore dell'enumerazione <xref:System.ServiceModel.Security.MessageProtectionOrder>. Il valore predefinito è <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Questo processo può richiedere fino al 30 percento in più del tempo necessario per eseguire la firma e la crittografia in base alla dimensione globale del messaggio (minore è la dimensione del messaggio, maggiore sarà l'impatto sulle prestazioni). La disattivazione della crittografia della firma può tuttavia consentire a un utente malintenzionato di intuire il contenuto del messaggio poiché l'elemento di firma contiene il codice hash del testo normale di ogni parte firmata del messaggio. Ad esempio, anche se il corpo del messaggio viene crittografato per impostazione predefinita, la firma non crittografata contiene il codice hash del corpo del messaggio prima della crittografia. Se il set di valori possibili per la parte firmata e crittografata è limitato, un utente malintenzionato può essere in grado di dedurre il contenuto analizzando il valore hash. La crittografia della firma consente di ridurre il rischio di attacchi.  
  
 È consigliabile quindi disattivare la crittografia della firma soltanto quando il valore del contenuto è basso o il set di valori possibili del contenuto è ampio e non deterministico e il livello delle prestazioni è più importante rispetto alla riduzione del rischio di attacchi descritto sopra.  
  
> [!NOTE]
> Se il messaggio non contiene alcun elemento crittografato, l'elemento di firma non viene crittografato, anche quando la proprietà <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> è impostata su <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Questo comportamento si verifica anche con le associazioni fornite dal sistema. Per tutte le associazioni fornite dal sistema l'ordine di protezione dei messaggi è impostato su `SignBeforeEncryptAndEncryptSignature`. Tuttavia, il Web Services Description Language (WSDL) generato da WCF conterrà comunque l' `<sp:EncryptSignature>` asserzione.  
  
### <a name="to-disable-digital-signing"></a>Per disattivare la firma digitale  
  
1. Creare un oggetto <xref:System.ServiceModel.Channels.CustomBinding>. Per altre informazioni, vedere [procedura: creare un'associazione personalizzata usando SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2. Aggiungere un elemento <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> alla raccolta di associazioni.  
  
3. Impostare la proprietà <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> oppure impostare la proprietà <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.  
  
## <a name="see-also"></a>Vedere anche

- [Funzionalità di sicurezza con associazioni personalizzate](security-capabilities-with-custom-bindings.md)
