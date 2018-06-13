---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: c2fb32c4c693cbfc487ce89b36f013398cbdb703
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485619"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="9956f-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="9956f-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="9956f-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="9956f-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9956f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9956f-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9956f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="9956f-105">Methods</span></span>  
 <span data-ttu-id="9956f-106">La classe TransactionFlowBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="9956f-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9956f-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9956f-107">Properties</span></span>  
 <span data-ttu-id="9956f-108">La classe TransactionFlowBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="9956f-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="9956f-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="9956f-109">IssuedTokens</span></span>  
 <span data-ttu-id="9956f-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9956f-110">Data type: string</span></span>  
  
 <span data-ttu-id="9956f-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9956f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9956f-112">Specifica il requisito per un'intestazione dei token di sicurezza emessi (IssuedTokens da WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="9956f-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="9956f-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="9956f-113">TransactionProtocol</span></span>  
 <span data-ttu-id="9956f-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9956f-114">Data type: string</span></span>  
  
 <span data-ttu-id="9956f-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9956f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9956f-116">Protocollo delle transazioni utilizzato dal servizio per il flusso delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="9956f-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="9956f-117">Transazioni</span><span class="sxs-lookup"><span data-stu-id="9956f-117">Transactions</span></span>  
 <span data-ttu-id="9956f-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="9956f-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="9956f-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9956f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9956f-120">Indica se la transazione in ingresso è supportata.</span><span class="sxs-lookup"><span data-stu-id="9956f-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9956f-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9956f-121">Requirements</span></span>  
  
|<span data-ttu-id="9956f-122">MOF</span><span class="sxs-lookup"><span data-stu-id="9956f-122">MOF</span></span>|<span data-ttu-id="9956f-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9956f-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9956f-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="9956f-124">Namespace</span></span>|<span data-ttu-id="9956f-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9956f-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9956f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9956f-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
