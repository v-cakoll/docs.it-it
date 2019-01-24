---
title: "Procedura: Set un'inclinazione di Clock massima"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: 73c3bd7c8bf02fd003510c838fec45a68829fe1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646877"
---
# <a name="how-to-set-a-max-clock-skew"></a>Procedura: Set un'inclinazione di Clock massima
È possibile un malfunzionamento delle funzioni dipendenti dall'orario quando le impostazioni dell'orologio in due computer sono differenti. Per limitare questo problema, è possibile impostare la proprietà `MaxClockSkew` su un <xref:System.TimeSpan>. Questa proprietà è disponibile in due classi:  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
>  Importante per una conversazione sicura, le modifiche per il `MaxClockSkew` proprietà deve essere apportata quando il servizio o il client viene avviato automaticamente. A tale scopo, è necessario impostare la proprietà sul <xref:System.ServiceModel.Channels.SecurityBindingElement> restituito dal <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.  
  
 Per modificare la proprietà in una delle associazioni fornite dal sistema, è necessario trovare l'elemento di associazione di sicurezza nella raccolta di associazioni e impostare la proprietà `MaxClockSkew` su un valore nuovo. Le due classi derivano da <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> e <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Quando si recupera l'associazione di sicurezza dalla raccolta, è necessario eseguire il cast a uno di questi tipi per impostare correttamente la proprietà `MaxClockSkew`. Nell'esempio seguente viene utilizzato <xref:System.ServiceModel.WSHttpBinding> che utilizza <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>. Per un elenco che specifica quale tipo di associazione di sicurezza da usare in ogni associazione fornita dal sistema, vedere [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
### <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a>Per creare un'associazione personalizzata con un nuovo valore dello sfasamento dei segnali di clock nel codice  
  
1.  > [!WARNING]
    >  Nota aggiungere riferimenti agli spazi dei nomi seguenti nel codice: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, e <xref:System.ServiceModel.Security.Tokens>.  
  
     Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e impostarne la modalità di sicurezza su <xref:System.ServiceModel.SecurityMode.Message>.  
  
2.  Creare una nuova istanza della classe <xref:System.ServiceModel.Channels.BindingElementCollection> chiamando il metodo <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.  
  
3.  Utilizzare il metodo <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> della classe <xref:System.ServiceModel.Channels.BindingElementCollection> per trovare l'elemento di associazione di sicurezza.  
  
4.  Quando si utilizza il metodo <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>, eseguire il cast al tipo effettivo. Nell'esempio seguente viene eseguito il cast al tipo <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
5.  Impostare la proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> sull'elemento di associazione di sicurezza.  
  
6.  Creare un <xref:System.ServiceModel.ServiceHost> con un tipo di servizio e un indirizzo di base appropriati.  
  
7.  Utilizzare il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> per aggiungere un endpoint e includere <xref:System.ServiceModel.Channels.CustomBinding>.  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
### <a name="to-set-the-maxclockskew-in-configuration"></a>Per impostare MaxClockSkew nella configurazione  
  
1.  Creare un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) nel [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) sezione dell'elemento.  
  
2.  Creare un [ \<associazione >](../../../../docs/framework/misc/binding.md) e impostare il `name` attributo su un valore appropriato. Nell'esempio seguente viene impostato su `MaxClockSkewBinding`.  
  
3.  Aggiungere un elemento di codifica. L'esempio seguente aggiunge un [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
4.  Aggiungere un [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) e impostare il `authenticationMode` attributo un'impostazione appropriata. Nell'esempio seguente l'attributo viene impostato su `Kerberos` per specificare che il servizio utilizza l'autenticazione di Windows.  
  
5.  Aggiungere un [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) e impostare il `maxClockSkew` attributo su un valore sotto forma di `"##:##:##"`. Nell'esempio seguente viene impostato su 7 minuti. Facoltativamente, aggiungere un [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) e impostare il `maxClockSkew` attributo un'impostazione appropriata.  
  
6.  Aggiungere un elemento trasporto. L'esempio seguente usa un' [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
7.  Per una conversazione sicura, le impostazioni di sicurezza devono verificarsi all'avvio in automatico il [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento.  
  
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
- [Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
