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
# <a name="how-to-set-a-max-clock-skew"></a><span data-ttu-id="ed66a-102">Procedura: impostare lo sfasamento massimo dei segnali di clock</span><span class="sxs-lookup"><span data-stu-id="ed66a-102">How to: Set a Max Clock Skew</span></span>
<span data-ttu-id="ed66a-103">È possibile un malfunzionamento delle funzioni dipendenti dall'orario quando le impostazioni dell'orologio in due computer sono differenti.</span><span class="sxs-lookup"><span data-stu-id="ed66a-103">Time-critical functions can be derailed if the clock settings on two computers are different.</span></span> <span data-ttu-id="ed66a-104">Per limitare questo problema, è possibile impostare la proprietà `MaxClockSkew` su un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="ed66a-104">To mitigate this possibility, you can set the `MaxClockSkew` property to a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="ed66a-105">Questa proprietà è disponibile in due classi:</span><span class="sxs-lookup"><span data-stu-id="ed66a-105">This property is available on two classes:</span></span>  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
> <span data-ttu-id="ed66a-106">Per una conversazione protetta, è necessario apportare modifiche alla `MaxClockSkew` proprietà quando il servizio o il client viene bootstrap.</span><span class="sxs-lookup"><span data-stu-id="ed66a-106">For a secure conversation, changes to the `MaxClockSkew` property  must be made when the service or client is bootstrapped.</span></span> <span data-ttu-id="ed66a-107">A tale scopo, è necessario impostare la proprietà sull'oggetto <xref:System.ServiceModel.Channels.SecurityBindingElement> restituito dalla <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="ed66a-107">To do this, you must set the property on the <xref:System.ServiceModel.Channels.SecurityBindingElement> returned by the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="ed66a-108">Per modificare la proprietà in una delle associazioni fornite dal sistema, è necessario trovare l'elemento di associazione di sicurezza nella raccolta di associazioni e impostare la proprietà `MaxClockSkew` su un valore nuovo.</span><span class="sxs-lookup"><span data-stu-id="ed66a-108">To change the property on one of the system-provided bindings, you must find the security binding element in the collection of bindings and set the `MaxClockSkew` property to a new value.</span></span> <span data-ttu-id="ed66a-109">Le due classi derivano da <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> e <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ed66a-109">Two classes derive from the <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="ed66a-110">Quando si recupera l'associazione di sicurezza dalla raccolta, è necessario eseguire il cast a uno di questi tipi per impostare correttamente la proprietà `MaxClockSkew`.</span><span class="sxs-lookup"><span data-stu-id="ed66a-110">When retrieving the security binding from the collection, you must cast to one of these types in order to correctly set the `MaxClockSkew` property.</span></span> <span data-ttu-id="ed66a-111">Nell'esempio seguente viene utilizzato <xref:System.ServiceModel.WSHttpBinding> che utilizza <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ed66a-111">The following example uses a <xref:System.ServiceModel.WSHttpBinding>, which uses the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="ed66a-112">Per un elenco che specifica quale tipo di associazione di sicurezza utilizzare in ogni associazione fornita dal sistema, vedere [associazioni fornite dal sistema](../system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="ed66a-112">For a list that specifies which type of security binding to use in each system-provided binding, see [System-Provided Bindings](../system-provided-bindings.md).</span></span>  
  
## <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a><span data-ttu-id="ed66a-113">Per creare un'associazione personalizzata con un nuovo valore dello sfasamento dei segnali di clock nel codice</span><span class="sxs-lookup"><span data-stu-id="ed66a-113">To create a custom binding with a new clock skew value in code</span></span>  
  
> [!WARNING]
> <span data-ttu-id="ed66a-114">Aggiungere i riferimenti agli spazi dei nomi seguenti nel codice: <xref:System.ServiceModel.Channels> , <xref:System.ServiceModel.Description> , <xref:System.Security.Permissions> e <xref:System.ServiceModel.Security.Tokens> .</span><span class="sxs-lookup"><span data-stu-id="ed66a-114">Add references to the following namespaces in your code: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, and <xref:System.ServiceModel.Security.Tokens>.</span></span>  
  
1. <span data-ttu-id="ed66a-115">Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e impostarne la modalità di sicurezza su <xref:System.ServiceModel.SecurityMode.Message?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ed66a-115">Create an instance of a <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message?displayProperty=nameWithType>.</span></span>  
  
2. <span data-ttu-id="ed66a-116">Creare una nuova istanza della classe <xref:System.ServiceModel.Channels.BindingElementCollection> chiamando il metodo <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="ed66a-116">Create a new instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class by calling the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3. <span data-ttu-id="ed66a-117">Utilizzare il metodo <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> della classe <xref:System.ServiceModel.Channels.BindingElementCollection> per trovare l'elemento di associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ed66a-117">Use the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method of the <xref:System.ServiceModel.Channels.BindingElementCollection> class to find the security binding element.</span></span>  
  
4. <span data-ttu-id="ed66a-118">Quando si utilizza il metodo <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>, eseguire il cast al tipo effettivo.</span><span class="sxs-lookup"><span data-stu-id="ed66a-118">When using the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method, cast to the actual type.</span></span> <span data-ttu-id="ed66a-119">Nell'esempio seguente viene eseguito il cast al tipo <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ed66a-119">The example below casts to the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> type.</span></span>  
  
5. <span data-ttu-id="ed66a-120">Impostare la proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> sull'elemento di associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ed66a-120">Set the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> property on the security binding element.</span></span>  
  
6. <span data-ttu-id="ed66a-121">Creare un <xref:System.ServiceModel.ServiceHost> con un tipo di servizio e un indirizzo di base appropriati.</span><span class="sxs-lookup"><span data-stu-id="ed66a-121">Create a <xref:System.ServiceModel.ServiceHost> with an appropriate service type and base address.</span></span>  
  
7. <span data-ttu-id="ed66a-122">Utilizzare il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> per aggiungere un endpoint e includere <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="ed66a-122">Use the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method to add an endpoint and include the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
## <a name="to-set-the-maxclockskew-in-configuration"></a><span data-ttu-id="ed66a-123">Per impostare MaxClockSkew nella configurazione</span><span class="sxs-lookup"><span data-stu-id="ed66a-123">To set the MaxClockSkew in configuration</span></span>  
  
1. <span data-ttu-id="ed66a-124">Creare un oggetto [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) nella [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) sezione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="ed66a-124">Create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) in the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element section.</span></span>  
  
2. <span data-ttu-id="ed66a-125">Creare un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento e impostare l' `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="ed66a-125">Create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="ed66a-126">Nell'esempio seguente viene impostato su `MaxClockSkewBinding`.</span><span class="sxs-lookup"><span data-stu-id="ed66a-126">The following example sets it to `MaxClockSkewBinding`.</span></span>  
  
3. <span data-ttu-id="ed66a-127">Aggiungere un elemento di codifica.</span><span class="sxs-lookup"><span data-stu-id="ed66a-127">Add an encoding element.</span></span> <span data-ttu-id="ed66a-128">Nell'esempio seguente viene aggiunto un [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="ed66a-128">The example below adds a [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
4. <span data-ttu-id="ed66a-129">Aggiungere un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento e impostare l' `authenticationMode` attributo su un'impostazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="ed66a-129">Add a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element and set the `authenticationMode` attribute to an appropriate setting.</span></span> <span data-ttu-id="ed66a-130">Nell'esempio seguente l'attributo viene impostato su `Kerberos` per specificare che il servizio utilizza l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="ed66a-130">The following example set the attribute to `Kerberos` to specify that the service use Windows authentication.</span></span>  
  
5. <span data-ttu-id="ed66a-131">Aggiungere un oggetto [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) e impostare l' `maxClockSkew` attributo su un valore nel formato `"##:##:##"` .</span><span class="sxs-lookup"><span data-stu-id="ed66a-131">Add a [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to a value in the form of `"##:##:##"`.</span></span> <span data-ttu-id="ed66a-132">Nell'esempio seguente viene impostato su 7 minuti.</span><span class="sxs-lookup"><span data-stu-id="ed66a-132">The following example sets it to 7 minutes.</span></span> <span data-ttu-id="ed66a-133">Facoltativamente, aggiungere un [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) e impostare l' `maxClockSkew` attributo su un'impostazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="ed66a-133">Optionally, add a [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to an appropriate setting.</span></span>  
  
6. <span data-ttu-id="ed66a-134">Aggiungere un elemento trasporto.</span><span class="sxs-lookup"><span data-stu-id="ed66a-134">Add a transport element.</span></span> <span data-ttu-id="ed66a-135">Nell'esempio seguente viene usato un oggetto [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="ed66a-135">The following example uses an [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
7. <span data-ttu-id="ed66a-136">Per una conversazione sicura, le impostazioni di sicurezza devono essere eseguite in fase di bootstrap nell' [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ed66a-136">For a secure conversation, the security settings must occur at the bootstrap in the [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ed66a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed66a-137">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ed66a-138">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ed66a-138">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
