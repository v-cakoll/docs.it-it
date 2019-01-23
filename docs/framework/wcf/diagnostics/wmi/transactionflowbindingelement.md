---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: d0311837ebb8112d9492fb548492bcd3e10230e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514570"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="ed0d5-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="ed0d5-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="ed0d5-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="ed0d5-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed0d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed0d5-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ed0d5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ed0d5-105">Methods</span></span>  
 <span data-ttu-id="ed0d5-106">La classe TransactionFlowBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="ed0d5-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ed0d5-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ed0d5-107">Properties</span></span>  
 <span data-ttu-id="ed0d5-108">La classe TransactionFlowBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed0d5-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="ed0d5-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="ed0d5-109">IssuedTokens</span></span>  
 <span data-ttu-id="ed0d5-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ed0d5-110">Data type: string</span></span>  
  
 <span data-ttu-id="ed0d5-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ed0d5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed0d5-112">Specifica il requisito per un'intestazione dei token di sicurezza emessi (IssuedTokens da WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="ed0d5-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="ed0d5-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="ed0d5-113">TransactionProtocol</span></span>  
 <span data-ttu-id="ed0d5-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ed0d5-114">Data type: string</span></span>  
  
 <span data-ttu-id="ed0d5-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ed0d5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed0d5-116">Protocollo delle transazioni utilizzato dal servizio per il flusso delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ed0d5-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="ed0d5-117">Transazioni</span><span class="sxs-lookup"><span data-stu-id="ed0d5-117">Transactions</span></span>  
 <span data-ttu-id="ed0d5-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ed0d5-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="ed0d5-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ed0d5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed0d5-120">Indica se la transazione in ingresso è supportata.</span><span class="sxs-lookup"><span data-stu-id="ed0d5-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed0d5-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed0d5-121">Requirements</span></span>  
  
|<span data-ttu-id="ed0d5-122">MOF</span><span class="sxs-lookup"><span data-stu-id="ed0d5-122">MOF</span></span>|<span data-ttu-id="ed0d5-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ed0d5-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ed0d5-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ed0d5-124">Namespace</span></span>|<span data-ttu-id="ed0d5-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ed0d5-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed0d5-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed0d5-126">See also</span></span>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
