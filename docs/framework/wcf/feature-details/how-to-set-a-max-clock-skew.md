---
title: 'Procedura: Impostare lo sfasamento di orario massimo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: 1a8d99e5d2bd21a74318718f43b5d1c091ed073e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322147"
---
# <a name="how-to-set-a-max-clock-skew"></a><span data-ttu-id="fc6ac-102">Procedura: Impostare lo sfasamento di orario massimo</span><span class="sxs-lookup"><span data-stu-id="fc6ac-102">How to: Set a Max Clock Skew</span></span>
<span data-ttu-id="fc6ac-103">È possibile un malfunzionamento delle funzioni dipendenti dall'orario quando le impostazioni dell'orologio in due computer sono differenti.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-103">Time-critical functions can be derailed if the clock settings on two computers are different.</span></span> <span data-ttu-id="fc6ac-104">Per limitare questo problema, è possibile impostare la proprietà `MaxClockSkew` su un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-104">To mitigate this possibility, you can set the `MaxClockSkew` property to a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="fc6ac-105">Questa proprietà è disponibile in due classi:</span><span class="sxs-lookup"><span data-stu-id="fc6ac-105">This property is available on two classes:</span></span>  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fc6ac-106">Importante per una conversazione sicura, le modifiche per il `MaxClockSkew` proprietà deve essere apportata quando il servizio o il client viene avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-106">Important   For a secure conversation, changes to the `MaxClockSkew` property  must be made when the service or client is bootstrapped.</span></span> <span data-ttu-id="fc6ac-107">A tale scopo, è necessario impostare la proprietà sul <xref:System.ServiceModel.Channels.SecurityBindingElement> restituito dal <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-107">To do this, you must set the property on the <xref:System.ServiceModel.Channels.SecurityBindingElement> returned by the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.</span></span>  
  
 <span data-ttu-id="fc6ac-108">Per modificare la proprietà in una delle associazioni fornite dal sistema, è necessario trovare l'elemento di associazione di sicurezza nella raccolta di associazioni e impostare la proprietà `MaxClockSkew` su un valore nuovo.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-108">To change the property on one of the system-provided bindings, you must find the security binding element in the collection of bindings and set the `MaxClockSkew` property to a new value.</span></span> <span data-ttu-id="fc6ac-109">Le due classi derivano da <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> e <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-109">Two classes derive from the <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="fc6ac-110">Quando si recupera l'associazione di sicurezza dalla raccolta, è necessario eseguire il cast a uno di questi tipi per impostare correttamente la proprietà `MaxClockSkew`.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-110">When retrieving the security binding from the collection, you must cast to one of these types in order to correctly set the `MaxClockSkew` property.</span></span> <span data-ttu-id="fc6ac-111">Nell'esempio seguente viene utilizzato <xref:System.ServiceModel.WSHttpBinding> che utilizza <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-111">The following example uses a <xref:System.ServiceModel.WSHttpBinding>, which uses the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="fc6ac-112">Per un elenco che specifica quale tipo di associazione di sicurezza da usare in ogni associazione fornita dal sistema, vedere [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="fc6ac-112">For a list that specifies which type of security binding to use in each system-provided binding, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
### <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a><span data-ttu-id="fc6ac-113">Per creare un'associazione personalizzata con un nuovo valore dello sfasamento dei segnali di clock nel codice</span><span class="sxs-lookup"><span data-stu-id="fc6ac-113">To create a custom binding with a new clock skew value in code</span></span>  
  
1. > [!WARNING]
    >  <span data-ttu-id="fc6ac-114">Nota aggiungere riferimenti agli spazi dei nomi seguenti nel codice: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, e <xref:System.ServiceModel.Security.Tokens>.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-114">Note   Add references to the following namespaces in your code: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, and <xref:System.ServiceModel.Security.Tokens>.</span></span>  
  
     <span data-ttu-id="fc6ac-115">Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e impostarne la modalità di sicurezza su <xref:System.ServiceModel.SecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-115">Create an instance of a <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>  
  
2. <span data-ttu-id="fc6ac-116">Creare una nuova istanza della classe <xref:System.ServiceModel.Channels.BindingElementCollection> chiamando il metodo <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-116">Create a new instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class by calling the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3. <span data-ttu-id="fc6ac-117">Utilizzare il metodo <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> della classe <xref:System.ServiceModel.Channels.BindingElementCollection> per trovare l'elemento di associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-117">Use the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method of the <xref:System.ServiceModel.Channels.BindingElementCollection> class to find the security binding element.</span></span>  
  
4. <span data-ttu-id="fc6ac-118">Quando si utilizza il metodo <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>, eseguire il cast al tipo effettivo.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-118">When using the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method, cast to the actual type.</span></span> <span data-ttu-id="fc6ac-119">Nell'esempio seguente viene eseguito il cast al tipo <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-119">The example below casts to the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> type.</span></span>  
  
5. <span data-ttu-id="fc6ac-120">Impostare la proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> sull'elemento di associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-120">Set the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> property on the security binding element.</span></span>  
  
6. <span data-ttu-id="fc6ac-121">Creare un <xref:System.ServiceModel.ServiceHost> con un tipo di servizio e un indirizzo di base appropriati.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-121">Create a <xref:System.ServiceModel.ServiceHost> with an appropriate service type and base address.</span></span>  
  
7. <span data-ttu-id="fc6ac-122">Utilizzare il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> per aggiungere un endpoint e includere <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-122">Use the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method to add an endpoint and include the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
### <a name="to-set-the-maxclockskew-in-configuration"></a><span data-ttu-id="fc6ac-123">Per impostare MaxClockSkew nella configurazione</span><span class="sxs-lookup"><span data-stu-id="fc6ac-123">To set the MaxClockSkew in configuration</span></span>  
  
1. <span data-ttu-id="fc6ac-124">Creare un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) nel [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) sezione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-124">Create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) in the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section.</span></span>  
  
2. <span data-ttu-id="fc6ac-125">Creare un [ \<associazione >](../../../../docs/framework/misc/binding.md) e impostare il `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-125">Create a [\<binding>](../../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="fc6ac-126">Nell'esempio seguente viene impostato su `MaxClockSkewBinding`.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-126">The following example sets it to `MaxClockSkewBinding`.</span></span>  
  
3. <span data-ttu-id="fc6ac-127">Aggiungere un elemento di codifica.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-127">Add an encoding element.</span></span> <span data-ttu-id="fc6ac-128">L'esempio seguente aggiunge un [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span><span class="sxs-lookup"><span data-stu-id="fc6ac-128">The example below adds a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
4. <span data-ttu-id="fc6ac-129">Aggiungere un [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) e impostare il `authenticationMode` attributo un'impostazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-129">Add a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element and set the `authenticationMode` attribute to an appropriate setting.</span></span> <span data-ttu-id="fc6ac-130">Nell'esempio seguente l'attributo viene impostato su `Kerberos` per specificare che il servizio utilizza l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-130">The following example set the attribute to `Kerberos` to specify that the service use Windows authentication.</span></span>  
  
5. <span data-ttu-id="fc6ac-131">Aggiungere un [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) e impostare il `maxClockSkew` attributo su un valore sotto forma di `"##:##:##"`.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-131">Add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to a value in the form of `"##:##:##"`.</span></span> <span data-ttu-id="fc6ac-132">Nell'esempio seguente viene impostato su 7 minuti.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-132">The following example sets it to 7 minutes.</span></span> <span data-ttu-id="fc6ac-133">Facoltativamente, aggiungere un [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) e impostare il `maxClockSkew` attributo un'impostazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-133">Optionally, add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to an appropriate setting.</span></span>  
  
6. <span data-ttu-id="fc6ac-134">Aggiungere un elemento trasporto.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-134">Add a transport element.</span></span> <span data-ttu-id="fc6ac-135">L'esempio seguente usa un' [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span><span class="sxs-lookup"><span data-stu-id="fc6ac-135">The following example uses an [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
7. <span data-ttu-id="fc6ac-136">Per una conversazione sicura, le impostazioni di sicurezza devono verificarsi all'avvio in automatico il [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-136">For a secure conversation, the security settings must occur at the bootstrap in the [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc6ac-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc6ac-137">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="fc6ac-138">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="fc6ac-138">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
