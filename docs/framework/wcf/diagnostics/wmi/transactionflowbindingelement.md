---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: a58d5620abbb636480ceea3020552246ae284842
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641684"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="13a5e-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="13a5e-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="13a5e-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="13a5e-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13a5e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13a5e-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="13a5e-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="13a5e-105">Methods</span></span>  
 <span data-ttu-id="13a5e-106">La classe TransactionFlowBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="13a5e-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="13a5e-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="13a5e-107">Properties</span></span>  
 <span data-ttu-id="13a5e-108">La classe TransactionFlowBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="13a5e-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="13a5e-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="13a5e-109">IssuedTokens</span></span>  
 <span data-ttu-id="13a5e-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="13a5e-110">Data type: string</span></span>  
  
 <span data-ttu-id="13a5e-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="13a5e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="13a5e-112">Specifica il requisito per un'intestazione dei token di sicurezza emessi (IssuedTokens da WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="13a5e-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="13a5e-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="13a5e-113">TransactionProtocol</span></span>  
 <span data-ttu-id="13a5e-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="13a5e-114">Data type: string</span></span>  
  
 <span data-ttu-id="13a5e-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="13a5e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="13a5e-116">Protocollo delle transazioni utilizzato dal servizio per il flusso delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="13a5e-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="13a5e-117">Transazioni</span><span class="sxs-lookup"><span data-stu-id="13a5e-117">Transactions</span></span>  
 <span data-ttu-id="13a5e-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="13a5e-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="13a5e-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="13a5e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="13a5e-120">Indica se la transazione in ingresso è supportata.</span><span class="sxs-lookup"><span data-stu-id="13a5e-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13a5e-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13a5e-121">Requirements</span></span>  
  
|<span data-ttu-id="13a5e-122">MOF</span><span class="sxs-lookup"><span data-stu-id="13a5e-122">MOF</span></span>|<span data-ttu-id="13a5e-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="13a5e-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="13a5e-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="13a5e-124">Namespace</span></span>|<span data-ttu-id="13a5e-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="13a5e-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13a5e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13a5e-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
