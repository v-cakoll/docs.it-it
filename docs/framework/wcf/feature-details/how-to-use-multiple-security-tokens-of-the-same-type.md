---
title: 'Procedura: usare più token di sicurezza dello stesso tipo'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 25afbb268a0ef7772585a0f3829b56f135758b61
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45666353"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="90bbf-102">Procedura: usare più token di sicurezza dello stesso tipo</span><span class="sxs-lookup"><span data-stu-id="90bbf-102">How to: Use Multiple Security Tokens of the Same Type</span></span>
-   <span data-ttu-id="90bbf-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0 un messaggio del client contiene solo un token di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="90bbf-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, a client message only contained one token of any given type.</span></span> <span data-ttu-id="90bbf-104">Nella nuova versione, i messaggi del client possono contenere più token di uno stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="90bbf-104">Now client messages can contain multiple tokens of a type.</span></span> <span data-ttu-id="90bbf-105">In questo argomento viene illustrato come includere più token dello stesso tipo in un messaggio del client.</span><span class="sxs-lookup"><span data-stu-id="90bbf-105">This topic shows how to include multiple tokens of the same type in a client message.</span></span>  
  
-   <span data-ttu-id="90bbf-106">Si noti che non è possibile configurare un servizio in questo modo, in quanto un servizio può contenere un solo token di supporto.</span><span class="sxs-lookup"><span data-stu-id="90bbf-106">Note that you cannot configure a service in this way: a service can contain only one supporting token.</span></span>  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="90bbf-107">Per usare più token di sicurezza dello stesso tipo</span><span class="sxs-lookup"><span data-stu-id="90bbf-107">To use multiple security tokens of the same type</span></span>  
  
1.  <span data-ttu-id="90bbf-108">Creare una raccolta di elementi di associazione vuota in cui inserire i dati.</span><span class="sxs-lookup"><span data-stu-id="90bbf-108">Create an empty binding element collection to be populated.</span></span>  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  <span data-ttu-id="90bbf-109">Creare una classe <xref:System.ServiceModel.Channels.SecurityBindingElement> chiamando <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="90bbf-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span></span>  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  <span data-ttu-id="90bbf-110">Creare una raccolta <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="90bbf-110">Create a <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  <span data-ttu-id="90bbf-111">Aggiungere i token SAML alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="90bbf-111">Add SAML tokens to the collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  <span data-ttu-id="90bbf-112">Aggiungere la raccolta alla classe <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="90bbf-112">Add the collection to the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  <span data-ttu-id="90bbf-113">Aggiungere gli elementi di associazione alla relativa raccolta.</span><span class="sxs-lookup"><span data-stu-id="90bbf-113">Add binding elements to the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  <span data-ttu-id="90bbf-114">Restituire una nuova associazione personalizzata creata a partire dalla raccolta di elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="90bbf-114">Return a new custom binding created from the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a><span data-ttu-id="90bbf-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="90bbf-115">Example</span></span>  
 <span data-ttu-id="90bbf-116">Di seguito è riportato l'intero metodo descritto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="90bbf-116">The following is the entire method described by the preceding procedure.</span></span>  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="90bbf-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90bbf-117">See Also</span></span>  
 [<span data-ttu-id="90bbf-118">Architettura di sicurezza</span><span class="sxs-lookup"><span data-stu-id="90bbf-118">Security Architecture</span></span>](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
