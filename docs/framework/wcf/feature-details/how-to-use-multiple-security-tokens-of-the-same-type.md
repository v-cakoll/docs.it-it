---
title: 'Procedura: Usare più token di sicurezza dello stesso tipo'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
ms.openlocfilehash: 7de5d52587e1796ecfa05048024f8847a555655c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59976443"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="fa9ce-102">Procedura: Usare più token di sicurezza dello stesso tipo</span><span class="sxs-lookup"><span data-stu-id="fa9ce-102">How to: Use Multiple Security Tokens of the Same Type</span></span>
-   <span data-ttu-id="fa9ce-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0 un messaggio del client contiene solo un token di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, a client message only contained one token of any given type.</span></span> <span data-ttu-id="fa9ce-104">Nella nuova versione, i messaggi del client possono contenere più token di uno stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-104">Now client messages can contain multiple tokens of a type.</span></span> <span data-ttu-id="fa9ce-105">In questo argomento viene illustrato come includere più token dello stesso tipo in un messaggio del client.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-105">This topic shows how to include multiple tokens of the same type in a client message.</span></span>  
  
-   <span data-ttu-id="fa9ce-106">Si noti che non è possibile configurare un servizio in questo modo, in quanto un servizio può contenere un solo token di supporto.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-106">Note that you cannot configure a service in this way: a service can contain only one supporting token.</span></span>  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="fa9ce-107">Per usare più token di sicurezza dello stesso tipo</span><span class="sxs-lookup"><span data-stu-id="fa9ce-107">To use multiple security tokens of the same type</span></span>  
  
1. <span data-ttu-id="fa9ce-108">Creare una raccolta di elementi di associazione vuota in cui inserire i dati.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-108">Create an empty binding element collection to be populated.</span></span>  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2. <span data-ttu-id="fa9ce-109">Creare una classe <xref:System.ServiceModel.Channels.SecurityBindingElement> chiamando <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span></span>  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3. <span data-ttu-id="fa9ce-110">Creare una raccolta <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-110">Create a <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4. <span data-ttu-id="fa9ce-111">Aggiungere i token SAML alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-111">Add SAML tokens to the collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5. <span data-ttu-id="fa9ce-112">Aggiungere la raccolta alla classe <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-112">Add the collection to the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6. <span data-ttu-id="fa9ce-113">Aggiungere gli elementi di associazione alla relativa raccolta.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-113">Add binding elements to the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7. <span data-ttu-id="fa9ce-114">Restituire una nuova associazione personalizzata creata a partire dalla raccolta di elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-114">Return a new custom binding created from the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a><span data-ttu-id="fa9ce-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa9ce-115">Example</span></span>  
 <span data-ttu-id="fa9ce-116">Di seguito è riportato l'intero metodo descritto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="fa9ce-116">The following is the entire method described by the preceding procedure.</span></span>  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
