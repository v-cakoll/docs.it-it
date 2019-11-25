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
ms.openlocfilehash: df18f89ee18bfa33ecc0aced617d168c805e3515
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138569"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="1f9b1-102">Procedura: Specificare il tipo di credenziali client</span><span class="sxs-lookup"><span data-stu-id="1f9b1-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="1f9b1-103">Dopo avere impostato una modalità di sicurezza (trasporto o messaggio), è possibile impostare il tipo di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="1f9b1-104">Questa proprietà specifica il tipo di credenziali che il client deve fornire al servizio per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="1f9b1-105">Per ulteriori informazioni sull'impostazione della modalità di sicurezza (un passaggio necessario prima di impostare il tipo di credenziale client), vedere [How: Impostare la modalità di sicurezza ](how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1f9b1-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="1f9b1-106">Per impostare il tipo di credenziali client nel codice</span><span class="sxs-lookup"><span data-stu-id="1f9b1-106">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="1f9b1-107">Creare un'istanza dell'associazione che verrà utilizzata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="1f9b1-108">In questo esempio viene utilizzata l'associazione <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="1f9b1-109">Impostare la proprietà <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="1f9b1-110">In questo esempio viene utilizzata la modalità messaggio.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-110">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="1f9b1-111">Impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="1f9b1-112">In questo esempio viene impostata per utilizzare l'autenticazione di Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span><span class="sxs-lookup"><span data-stu-id="1f9b1-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="1f9b1-113">Per impostare il tipo di credenziali client nella configurazione</span><span class="sxs-lookup"><span data-stu-id="1f9b1-113">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="1f9b1-114">Aggiungere un elemento [\<system. serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) al file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-114">Add a [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="1f9b1-115">Come elemento figlio, aggiungere un elemento [\<bindings >](../configure-apps/file-schema/wcf/bindings.md) .</span><span class="sxs-lookup"><span data-stu-id="1f9b1-115">As a child element, add a [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="1f9b1-116">Aggiungere un'associazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-116">Add an appropriate binding.</span></span> <span data-ttu-id="1f9b1-117">Questo esempio usa l'elemento [\<wsHttpBinding >](../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="1f9b1-117">This example uses the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="1f9b1-118">Aggiungere un elemento [\<binding >](../configure-apps/file-schema/wcf/bindings.md) e impostare l'attributo `name` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-118">Add a [\<binding>](../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="1f9b1-119">In questo esempio viene utilizzato il nome "SecureBinding."</span><span class="sxs-lookup"><span data-stu-id="1f9b1-119">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="1f9b1-120">Aggiungere un'associazione `<security>`.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-120">Add a `<security>` binding.</span></span> <span data-ttu-id="1f9b1-121">Impostare l'attributo `mode` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="1f9b1-122">In questo esempio viene impostato su `"Message"`.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-122">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="1f9b1-123">Aggiungere un `<message>` o `<transport>` elemento, come determinato dalla modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="1f9b1-124">Impostare l'attributo `clientCredentialType` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="1f9b1-125">In questo esempio viene usato `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="1f9b1-125">This example uses `"Windows"`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1f9b1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f9b1-126">See also</span></span>

- [<span data-ttu-id="1f9b1-127">Protezione dei servizi</span><span class="sxs-lookup"><span data-stu-id="1f9b1-127">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="1f9b1-128">Procedura: Impostare la modalità di sicurezza </span><span class="sxs-lookup"><span data-stu-id="1f9b1-128">How to: Set the Security Mode</span></span>](how-to-set-the-security-mode.md)
