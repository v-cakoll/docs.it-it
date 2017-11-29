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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4c65eb1689d1411cb9083967b9a29c946b7568b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="a9be6-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="a9be6-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="a9be6-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="a9be6-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9be6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9be6-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a9be6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a9be6-105">Methods</span></span>  
 <span data-ttu-id="a9be6-106">La classe TransactionFlowBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="a9be6-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a9be6-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a9be6-107">Properties</span></span>  
 <span data-ttu-id="a9be6-108">La classe TransactionFlowBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9be6-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="a9be6-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="a9be6-109">IssuedTokens</span></span>  
 <span data-ttu-id="a9be6-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a9be6-110">Data type: string</span></span>  
  
 <span data-ttu-id="a9be6-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a9be6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a9be6-112">Specifica il requisito per un'intestazione dei token di sicurezza emessi (IssuedTokens da WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="a9be6-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="a9be6-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="a9be6-113">TransactionProtocol</span></span>  
 <span data-ttu-id="a9be6-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a9be6-114">Data type: string</span></span>  
  
 <span data-ttu-id="a9be6-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a9be6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a9be6-116">Protocollo delle transazioni utilizzato dal servizio per il flusso delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="a9be6-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="a9be6-117">Transazioni</span><span class="sxs-lookup"><span data-stu-id="a9be6-117">Transactions</span></span>  
 <span data-ttu-id="a9be6-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="a9be6-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="a9be6-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a9be6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a9be6-120">Indica se la transazione in ingresso è supportata.</span><span class="sxs-lookup"><span data-stu-id="a9be6-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9be6-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9be6-121">Requirements</span></span>  
  
|<span data-ttu-id="a9be6-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a9be6-122">MOF</span></span>|<span data-ttu-id="a9be6-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a9be6-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a9be6-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a9be6-124">Namespace</span></span>|<span data-ttu-id="a9be6-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a9be6-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9be6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9be6-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
