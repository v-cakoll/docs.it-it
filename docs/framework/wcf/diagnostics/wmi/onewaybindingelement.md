---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a43707f25a9ee1beb1ce7adac36a2c4a55cab6d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="onewaybindingelement"></a><span data-ttu-id="784ef-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="784ef-102">OneWayBindingElement</span></span>
<span data-ttu-id="784ef-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="784ef-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="784ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="784ef-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="784ef-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="784ef-105">Methods</span></span>  
 <span data-ttu-id="784ef-106">La classe OneWayBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="784ef-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="784ef-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="784ef-107">Properties</span></span>  
 <span data-ttu-id="784ef-108">La classe OneWayBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="784ef-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="784ef-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="784ef-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="784ef-110">Tipo di dati: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="784ef-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="784ef-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="784ef-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="784ef-112">Impostazioni del pool di canali.</span><span class="sxs-lookup"><span data-stu-id="784ef-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="784ef-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="784ef-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="784ef-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="784ef-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="784ef-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="784ef-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="784ef-116">Numero massimo di canali accettati.</span><span class="sxs-lookup"><span data-stu-id="784ef-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="784ef-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="784ef-117">PacketRoutable</span></span>  
 <span data-ttu-id="784ef-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="784ef-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="784ef-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="784ef-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="784ef-120">Valore che indica se il pacchetto è instradabile.</span><span class="sxs-lookup"><span data-stu-id="784ef-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="784ef-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="784ef-121">Requirements</span></span>  
  
|<span data-ttu-id="784ef-122">MOF</span><span class="sxs-lookup"><span data-stu-id="784ef-122">MOF</span></span>|<span data-ttu-id="784ef-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="784ef-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="784ef-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="784ef-124">Namespace</span></span>|<span data-ttu-id="784ef-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="784ef-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="784ef-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="784ef-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
