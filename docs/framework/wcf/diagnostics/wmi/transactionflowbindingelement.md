---
title: TransactionFlowBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa5394e874e35b80b01796642e18d69c71e867dc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="a6bd8-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="a6bd8-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="a6bd8-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="a6bd8-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6bd8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6bd8-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a6bd8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a6bd8-105">Methods</span></span>  
 <span data-ttu-id="a6bd8-106">La classe TransactionFlowBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="a6bd8-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a6bd8-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a6bd8-107">Properties</span></span>  
 <span data-ttu-id="a6bd8-108">La classe TransactionFlowBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6bd8-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="a6bd8-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="a6bd8-109">IssuedTokens</span></span>  
 <span data-ttu-id="a6bd8-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a6bd8-110">Data type: string</span></span>  
  
 <span data-ttu-id="a6bd8-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a6bd8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a6bd8-112">Specifica il requisito per un'intestazione dei token di sicurezza emessi (IssuedTokens da WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="a6bd8-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="a6bd8-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="a6bd8-113">TransactionProtocol</span></span>  
 <span data-ttu-id="a6bd8-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a6bd8-114">Data type: string</span></span>  
  
 <span data-ttu-id="a6bd8-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a6bd8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a6bd8-116">Protocollo delle transazioni utilizzato dal servizio per il flusso delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="a6bd8-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="a6bd8-117">Transazioni</span><span class="sxs-lookup"><span data-stu-id="a6bd8-117">Transactions</span></span>  
 <span data-ttu-id="a6bd8-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="a6bd8-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="a6bd8-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a6bd8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a6bd8-120">Indica se la transazione in ingresso è supportata.</span><span class="sxs-lookup"><span data-stu-id="a6bd8-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6bd8-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6bd8-121">Requirements</span></span>  
  
|<span data-ttu-id="a6bd8-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a6bd8-122">MOF</span></span>|<span data-ttu-id="a6bd8-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a6bd8-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a6bd8-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a6bd8-124">Namespace</span></span>|<span data-ttu-id="a6bd8-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a6bd8-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6bd8-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6bd8-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
