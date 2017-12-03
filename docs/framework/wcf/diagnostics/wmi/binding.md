---
title: Binding2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9e44d161e1229db9145f4ed7e337396bbd98c68
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="binding"></a><span data-ttu-id="b96f5-102">Binding</span><span class="sxs-lookup"><span data-stu-id="b96f5-102">Binding</span></span>
<span data-ttu-id="b96f5-103">Associazione wmi</span><span class="sxs-lookup"><span data-stu-id="b96f5-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b96f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b96f5-104">Syntax</span></span>  
  
```  
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b96f5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b96f5-105">Methods</span></span>  
 <span data-ttu-id="b96f5-106">La classe Binding non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="b96f5-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b96f5-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b96f5-107">Properties</span></span>  
 <span data-ttu-id="b96f5-108">La classe Binding dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="b96f5-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="b96f5-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="b96f5-109">BindingElements</span></span>  
 <span data-ttu-id="b96f5-110">Tipo di dati: matrice di BindingElement</span><span class="sxs-lookup"><span data-stu-id="b96f5-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="b96f5-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b96f5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b96f5-112">Raccolta di elementi di associazione implementati dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="b96f5-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="b96f5-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="b96f5-113">CloseTimeout</span></span>  
 <span data-ttu-id="b96f5-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="b96f5-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="b96f5-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b96f5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b96f5-116">Intervallo di tempo consentito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="b96f5-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="b96f5-117">Nome</span><span class="sxs-lookup"><span data-stu-id="b96f5-117">Name</span></span>  
 <span data-ttu-id="b96f5-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="b96f5-118">Data type: string</span></span>  
  
 <span data-ttu-id="b96f5-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b96f5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b96f5-120">Nome dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="b96f5-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="b96f5-121">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="b96f5-121">Namespace</span></span>  
 <span data-ttu-id="b96f5-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="b96f5-122">Data type: string</span></span>  
  
 <span data-ttu-id="b96f5-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b96f5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b96f5-124">Spazio dei nomi XML dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="b96f5-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="b96f5-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="b96f5-125">OpenTimeout</span></span>  
 <span data-ttu-id="b96f5-126">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="b96f5-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="b96f5-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b96f5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b96f5-128">Intervallo di tempo consentito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="b96f5-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="b96f5-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="b96f5-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="b96f5-130">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="b96f5-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="b96f5-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b96f5-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b96f5-132">Intervallo di tempo consentito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="b96f5-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="b96f5-133">Scheme</span><span class="sxs-lookup"><span data-stu-id="b96f5-133">Scheme</span></span>  
 <span data-ttu-id="b96f5-134">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="b96f5-134">Data type: string</span></span>  
  
 <span data-ttu-id="b96f5-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b96f5-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b96f5-136">Schema di trasporto URI utilizzato dalla channel factory e dalla listener factory generate dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="b96f5-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="b96f5-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="b96f5-137">SendTimeout</span></span>  
 <span data-ttu-id="b96f5-138">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="b96f5-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="b96f5-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="b96f5-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b96f5-140">Intervallo di tempo consentito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="b96f5-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b96f5-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b96f5-141">Requirements</span></span>  
  
|<span data-ttu-id="b96f5-142">MOF</span><span class="sxs-lookup"><span data-stu-id="b96f5-142">MOF</span></span>|<span data-ttu-id="b96f5-143">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b96f5-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b96f5-144">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="b96f5-144">Namespace</span></span>|<span data-ttu-id="b96f5-145">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b96f5-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b96f5-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b96f5-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>
