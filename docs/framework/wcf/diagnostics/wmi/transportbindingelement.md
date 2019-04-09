---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: bdb5ca7400a41dd724c2ad7fc76695a82874ded6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112372"
---
# <a name="transportbindingelement"></a><span data-ttu-id="cffff-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cffff-102">TransportBindingElement</span></span>
<span data-ttu-id="cffff-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="cffff-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cffff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cffff-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cffff-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="cffff-105">Methods</span></span>  
 <span data-ttu-id="cffff-106">La classe TransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="cffff-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cffff-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cffff-107">Properties</span></span>  
 <span data-ttu-id="cffff-108">La classe TransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="cffff-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="cffff-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="cffff-109">ManualAddressing</span></span>  
 <span data-ttu-id="cffff-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="cffff-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="cffff-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cffff-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cffff-112">Valore booleano che specifica se l'utente desidera controllare l'indirizzamento dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="cffff-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="cffff-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="cffff-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="cffff-114">Tipo di dati: sint64</span><span class="sxs-lookup"><span data-stu-id="cffff-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="cffff-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cffff-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cffff-116">Dimensioni massime del pool di buffer dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="cffff-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="cffff-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="cffff-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="cffff-118">Tipo di dati: sint64</span><span class="sxs-lookup"><span data-stu-id="cffff-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="cffff-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cffff-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cffff-120">Dimensioni massime di un messaggio elaborato dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="cffff-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="cffff-121">Scheme</span><span class="sxs-lookup"><span data-stu-id="cffff-121">Scheme</span></span>  
 <span data-ttu-id="cffff-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="cffff-122">Data type: string</span></span>  
  
 <span data-ttu-id="cffff-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="cffff-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cffff-124">Schema URI del trasporto.</span><span class="sxs-lookup"><span data-stu-id="cffff-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cffff-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cffff-125">Requirements</span></span>  
  
|<span data-ttu-id="cffff-126">MOF</span><span class="sxs-lookup"><span data-stu-id="cffff-126">MOF</span></span>|<span data-ttu-id="cffff-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cffff-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cffff-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="cffff-128">Namespace</span></span>|<span data-ttu-id="cffff-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cffff-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cffff-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cffff-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
