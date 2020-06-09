---
title: 'Procedura: creare un elemento SecurityBindingElement per una modalità di autenticazione specificata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
ms.openlocfilehash: 9aebe6d8cc82c454161daead49b55f02a1cca4a7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598944"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="5d7b4-102">Procedura: creare un elemento SecurityBindingElement per una modalità di autenticazione specificata</span><span class="sxs-lookup"><span data-stu-id="5d7b4-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>
<span data-ttu-id="5d7b4-103">Windows Communication Foundation (WCF) offre diverse modalità di autenticazione tra client e servizi.</span><span class="sxs-lookup"><span data-stu-id="5d7b4-103">Windows Communication Foundation (WCF) provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="5d7b4-104">È possibile creare elementi di associazione di sicurezza per tali modalità di autenticazione utilizzando metodi statici sulla classe <xref:System.ServiceModel.Channels.SecurityBindingElement> o tramite configurazione, come spiegato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5d7b4-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="5d7b4-105">Per altre informazioni sulle 18 modalità di autenticazione, vedere [modalità di autenticazione di SecurityBindingElement](securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="5d7b4-105">For more information about the 18 authentication modes, see [SecurityBindingElement Authentication Modes](securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d7b4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d7b4-106">Example</span></span>  
 <span data-ttu-id="5d7b4-107">Nell'esempio di codice seguente sono illustrati i metodi per la creazione di associazioni per le varie modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5d7b4-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d7b4-108">Dopo la creazione di un'istanza dell'oggetto <xref:System.ServiceModel.Channels.SecurityBindingElement>, diverse proprietà sono immutabili, ad esempio <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> e <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d7b4-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="5d7b4-109">Non cambiano neppure chiamando `set` su di esse.</span><span class="sxs-lookup"><span data-stu-id="5d7b4-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5d7b4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d7b4-110">See also</span></span>

- [<span data-ttu-id="5d7b4-111">Modalità di autenticazione di SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5d7b4-111">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)
- [<span data-ttu-id="5d7b4-112">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5d7b4-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
