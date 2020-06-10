---
title: "Procedura: disattivare sessioni protette in un'associazione WSFederationHttpBinding"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
ms.openlocfilehash: df057d64feb89d1e43b938b36cb48f2f103b17d0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595388"
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a>Procedura: disattivare sessioni protette in un'associazione WSFederationHttpBinding

Alcuni servizi possono richiedere credenziali federate senza tuttavia supportare le sessioni protette. In questo caso occorre disattivare la funzionalità di sessione protetta. A differenza della classe <xref:System.ServiceModel.WSHttpBinding>, la classe <xref:System.ServiceModel.WSFederationHttpBinding> non fornisce alcuna modalità di disattivazione delle sessioni protette quando si comunica con un servizio. È invece necessario creare un'associazione personalizzata che sostituisce le impostazioni della sessione protetta con un bootstrap.

Questo argomento illustra come modificare gli elementi di un'associazione <xref:System.ServiceModel.WSFederationHttpBinding> per creare un'associazione personalizzata. Il risultato è un'associazione <xref:System.ServiceModel.WSFederationHttpBinding> uguale all'originale in cui tuttavia non vengono utilizzate sessioni protette.

## <a name="to-create-a-custom-federated-binding-without-secure-session"></a>Per creare un'associazione federata personalizzata senza sessioni protette

1. Creare un'istanza della classe <xref:System.ServiceModel.WSFederationHttpBinding> o in modo imperativo nel codice oppure caricando un'associazione di questo tipo dal file di configurazione.

2. Duplicare l'associazione <xref:System.ServiceModel.WSFederationHttpBinding> in un'associazione <xref:System.ServiceModel.Channels.CustomBinding>.

3. Individuare l'elemento <xref:System.ServiceModel.Channels.SecurityBindingElement> all'interno dell'associazione <xref:System.ServiceModel.Channels.CustomBinding>.

4. Individuare l'elemento <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> all'interno dell'associazione <xref:System.ServiceModel.Channels.SecurityBindingElement>.

5. Sostituire l'elemento <xref:System.ServiceModel.Channels.SecurityBindingElement> originale con l'elemento di associazione di sicurezza bootstrap ottenuto dai parametri <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.

## <a name="example"></a>Esempio

Nell'esempio seguente viene creata un'associazione federata personalizzata senza sessioni protette.

[!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
[!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]

## <a name="compiling-the-code"></a>Compilazione del codice

- Per compilare l'esempio di codice, creare un progetto che fa riferimento all'assembly System.ServiceModel.dll.

## <a name="see-also"></a>Vedere anche

- [Associazioni e protezione](bindings-and-security.md)
