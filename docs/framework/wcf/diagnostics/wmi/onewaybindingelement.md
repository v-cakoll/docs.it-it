---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: d84184febd6db3f233aae6fe558b8e0f50a9cb82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608836"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="7efc4-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="7efc4-102">OneWayBindingElement</span></span>
<span data-ttu-id="7efc4-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="7efc4-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7efc4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7efc4-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7efc4-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7efc4-105">Methods</span></span>  
 <span data-ttu-id="7efc4-106">La classe OneWayBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="7efc4-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7efc4-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7efc4-107">Properties</span></span>  
 <span data-ttu-id="7efc4-108">La classe OneWayBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="7efc4-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="7efc4-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7efc4-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="7efc4-110">Tipo di dati: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7efc4-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="7efc4-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="7efc4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7efc4-112">Impostazioni del pool di canali.</span><span class="sxs-lookup"><span data-stu-id="7efc4-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="7efc4-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="7efc4-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="7efc4-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="7efc4-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="7efc4-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="7efc4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7efc4-116">Numero massimo di canali accettati.</span><span class="sxs-lookup"><span data-stu-id="7efc4-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="7efc4-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="7efc4-117">PacketRoutable</span></span>  
 <span data-ttu-id="7efc4-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="7efc4-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="7efc4-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="7efc4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7efc4-120">Valore che indica se il pacchetto è instradabile.</span><span class="sxs-lookup"><span data-stu-id="7efc4-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7efc4-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7efc4-121">Requirements</span></span>  
  
|<span data-ttu-id="7efc4-122">MOF</span><span class="sxs-lookup"><span data-stu-id="7efc4-122">MOF</span></span>|<span data-ttu-id="7efc4-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7efc4-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7efc4-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="7efc4-124">Namespace</span></span>|<span data-ttu-id="7efc4-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7efc4-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7efc4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7efc4-126">See also</span></span>
- <xref:System.ServiceModel.Channels.OneWayBindingElement>
