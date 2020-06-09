---
title: 'Procedura: impostare lo sfasamento massimo dei segnali di clock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: f8231acade6821c95a76a608633fe443f4add8ab
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586915"
---
# <a name="how-to-set-a-max-clock-skew"></a>Procedura: impostare lo sfasamento massimo dei segnali di clock
È possibile un malfunzionamento delle funzioni dipendenti dall'orario quando le impostazioni dell'orologio in due computer sono differenti. Per limitare questo problema, è possibile impostare la proprietà `MaxClockSkew` su un <xref:System.TimeSpan>. Questa proprietà è disponibile in due classi:  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
> Per una conversazione protetta, è necessario apportare modifiche alla `MaxClockSkew` proprietà quando il servizio o il client viene bootstrap. A tale scopo, è necessario impostare la proprietà sull'oggetto <xref:System.ServiceModel.Channels.SecurityBindingElement> restituito dalla <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A?displayProperty=nameWithType> Proprietà.  
  
 Per modificare la proprietà in una delle associazioni fornite dal sistema, è necessario trovare l'elemento di associazione di sicurezza nella raccolta di associazioni e impostare la proprietà `MaxClockSkew` su un valore nuovo. Le due classi derivano da <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> e <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Quando si recupera l'associazione di sicurezza dalla raccolta, è necessario eseguire il cast a uno di questi tipi per impostare correttamente la proprietà `MaxClockSkew`. Nell'esempio seguente viene utilizzato <xref:System.ServiceModel.WSHttpBinding> che utilizza <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>. Per un elenco che specifica quale tipo di associazione di sicurezza utilizzare in ogni associazione fornita dal sistema, vedere [associazioni fornite dal sistema](../system-provided-bindings.md).  
  
## <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a>Per creare un'associazione personalizzata con un nuovo valore dello sfasamento dei segnali di clock nel codice  
  
> [!WARNING]
> Aggiungere i riferimenti agli spazi dei nomi seguenti nel codice: <xref:System.ServiceModel.Channels> , <xref:System.ServiceModel.Description> , <xref:System.Security.Permissions> e <xref:System.ServiceModel.Security.Tokens> .  
  
1. Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e impostarne la modalità di sicurezza su <xref:System.ServiceModel.SecurityMode.Message?displayProperty=nameWithType>.  
  
2. Creare una nuova istanza della classe <xref:System.ServiceModel.Channels.BindingElementCollection> chiamando il metodo <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.  
  
3. Utilizzare il metodo <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> della classe <xref:System.ServiceModel.Channels.BindingElementCollection> per trovare l'elemento di associazione di sicurezza.  
  
4. Quando si utilizza il metodo <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>, eseguire il cast al tipo effettivo. Nell'esempio seguente viene eseguito il cast al tipo <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
5. Impostare la proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> sull'elemento di associazione di sicurezza.  
  
6. Creare un <xref:System.ServiceModel.ServiceHost> con un tipo di servizio e un indirizzo di base appropriati.  
  
7. Utilizzare il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> per aggiungere un endpoint e includere <xref:System.ServiceModel.Channels.CustomBinding>.  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
## <a name="to-set-the-maxclockskew-in-configuration"></a>Per impostare MaxClockSkew nella configurazione  
  
1. Creare un oggetto [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) nella [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) sezione dell'elemento.  
  
2. Creare un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento e impostare l' `name` attributo su un valore appropriato. Nell'esempio seguente viene impostato su `MaxClockSkewBinding`.  
  
3. Aggiungere un elemento di codifica. Nell'esempio seguente viene aggiunto un [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) .  
  
4. Aggiungere un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento e impostare l' `authenticationMode` attributo su un'impostazione appropriata. Nell'esempio seguente l'attributo viene impostato su `Kerberos` per specificare che il servizio utilizza l'autenticazione di Windows.  
  
5. Aggiungere un oggetto [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) e impostare l' `maxClockSkew` attributo su un valore nel formato `"##:##:##"` . Nell'esempio seguente viene impostato su 7 minuti. Facoltativamente, aggiungere un [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) e impostare l' `maxClockSkew` attributo su un'impostazione appropriata.  
  
6. Aggiungere un elemento trasporto. Nell'esempio seguente viene usato un oggetto [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) .  
  
7. Per una conversazione sicura, le impostazioni di sicurezza devono essere eseguite in fase di bootstrap nell' [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Procedura: creare un'associazione personalizzata usando SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
