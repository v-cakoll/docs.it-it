---
title: 'Procedura: Specificare il tipo di credenziali client'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: 775c6a297047c7a0e16db091f9a22686fdb01efb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928882"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="55b5a-102">Procedura: Specificare il tipo di credenziali client</span><span class="sxs-lookup"><span data-stu-id="55b5a-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="55b5a-103">Dopo avere impostato una modalità di sicurezza (trasporto o messaggio), è possibile impostare il tipo di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="55b5a-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="55b5a-104">Questa proprietà specifica il tipo di credenziali che il client deve fornire al servizio per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="55b5a-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="55b5a-105">Per altre informazioni sull'impostazione della modalità di sicurezza (un passaggio necessario prima impostare il tipo di credenziale client), vedere [come: Impostare la modalità di sicurezza](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="55b5a-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="55b5a-106">Per impostare il tipo di credenziali client nel codice</span><span class="sxs-lookup"><span data-stu-id="55b5a-106">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="55b5a-107">Creare un'istanza dell'associazione che verrà utilizzata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="55b5a-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="55b5a-108">In questo esempio viene utilizzata l'associazione <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="55b5a-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="55b5a-109">Impostare la proprietà <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="55b5a-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="55b5a-110">In questo esempio viene utilizzata la modalità messaggio.</span><span class="sxs-lookup"><span data-stu-id="55b5a-110">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="55b5a-111">Impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="55b5a-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="55b5a-112">In questo esempio viene impostata per utilizzare l'autenticazione di Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span><span class="sxs-lookup"><span data-stu-id="55b5a-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="55b5a-113">Per impostare il tipo di credenziali client nella configurazione</span><span class="sxs-lookup"><span data-stu-id="55b5a-113">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="55b5a-114">Aggiungere un [ \<System. ServiceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="55b5a-114">Add a [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="55b5a-115">Come elemento figlio, aggiungere un [ \<associazioni >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="55b5a-115">As a child element, add a [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="55b5a-116">Aggiungere un'associazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="55b5a-116">Add an appropriate binding.</span></span> <span data-ttu-id="55b5a-117">Questo esempio Usa la [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="55b5a-117">This example uses the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="55b5a-118">Aggiungere un [ \<associazione >](../../../docs/framework/misc/binding.md) e impostare il `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="55b5a-118">Add a [\<binding>](../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="55b5a-119">In questo esempio viene utilizzato il nome "SecureBinding."</span><span class="sxs-lookup"><span data-stu-id="55b5a-119">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="55b5a-120">Aggiungere un'associazione `<security>`.</span><span class="sxs-lookup"><span data-stu-id="55b5a-120">Add a `<security>` binding.</span></span> <span data-ttu-id="55b5a-121">Impostare l'attributo `mode` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="55b5a-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="55b5a-122">In questo esempio viene impostato su `"Message"`.</span><span class="sxs-lookup"><span data-stu-id="55b5a-122">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="55b5a-123">Aggiungere un `<message>` o `<transport>` elemento, come determinato dalla modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="55b5a-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="55b5a-124">Impostare l'attributo `clientCredentialType` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="55b5a-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="55b5a-125">In questo esempio viene usato `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="55b5a-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="55b5a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55b5a-126">See also</span></span>

- [<span data-ttu-id="55b5a-127">Protezione dei servizi</span><span class="sxs-lookup"><span data-stu-id="55b5a-127">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="55b5a-128">Procedura: Impostare la modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="55b5a-128">How to: Set the Security Mode</span></span>](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
