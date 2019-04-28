---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: bdb5ca7400a41dd724c2ad7fc76695a82874ded6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641619"
---
# <a name="transportbindingelement"></a><span data-ttu-id="4e5c3-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="4e5c3-102">TransportBindingElement</span></span>
<span data-ttu-id="4e5c3-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="4e5c3-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e5c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e5c3-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4e5c3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4e5c3-105">Methods</span></span>  
 <span data-ttu-id="4e5c3-106">La classe TransportBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4e5c3-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4e5c3-107">Properties</span></span>  
 <span data-ttu-id="4e5c3-108">La classe TransportBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e5c3-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="4e5c3-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="4e5c3-109">ManualAddressing</span></span>  
 <span data-ttu-id="4e5c3-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4e5c3-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="4e5c3-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4e5c3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e5c3-112">Valore booleano che specifica se l'utente desidera controllare l'indirizzamento dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="4e5c3-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="4e5c3-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="4e5c3-114">Tipo di dati: sint64</span><span class="sxs-lookup"><span data-stu-id="4e5c3-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="4e5c3-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4e5c3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e5c3-116">Dimensioni massime del pool di buffer dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="4e5c3-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="4e5c3-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="4e5c3-118">Tipo di dati: sint64</span><span class="sxs-lookup"><span data-stu-id="4e5c3-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="4e5c3-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4e5c3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e5c3-120">Dimensioni massime di un messaggio elaborato dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="4e5c3-121">Scheme</span><span class="sxs-lookup"><span data-stu-id="4e5c3-121">Scheme</span></span>  
 <span data-ttu-id="4e5c3-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4e5c3-122">Data type: string</span></span>  
  
 <span data-ttu-id="4e5c3-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4e5c3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e5c3-124">Schema URI del trasporto.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e5c3-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e5c3-125">Requirements</span></span>  
  
|<span data-ttu-id="4e5c3-126">MOF</span><span class="sxs-lookup"><span data-stu-id="4e5c3-126">MOF</span></span>|<span data-ttu-id="4e5c3-127">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4e5c3-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4e5c3-128">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="4e5c3-128">Namespace</span></span>|<span data-ttu-id="4e5c3-129">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4e5c3-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e5c3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e5c3-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
