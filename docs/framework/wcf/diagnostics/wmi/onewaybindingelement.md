---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 34220a3651819978f5f597fdc67d54630ec5e059
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50049295"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="a52ac-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="a52ac-102">OneWayBindingElement</span></span>
<span data-ttu-id="a52ac-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="a52ac-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a52ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a52ac-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a52ac-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a52ac-105">Methods</span></span>  
 <span data-ttu-id="a52ac-106">La classe OneWayBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="a52ac-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a52ac-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a52ac-107">Properties</span></span>  
 <span data-ttu-id="a52ac-108">La classe OneWayBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="a52ac-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="a52ac-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="a52ac-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="a52ac-110">Tipo di dati: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="a52ac-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="a52ac-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a52ac-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a52ac-112">Impostazioni del pool di canali.</span><span class="sxs-lookup"><span data-stu-id="a52ac-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="a52ac-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="a52ac-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="a52ac-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="a52ac-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="a52ac-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a52ac-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a52ac-116">Numero massimo di canali accettati.</span><span class="sxs-lookup"><span data-stu-id="a52ac-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="a52ac-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="a52ac-117">PacketRoutable</span></span>  
 <span data-ttu-id="a52ac-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="a52ac-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="a52ac-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a52ac-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a52ac-120">Valore che indica se il pacchetto è instradabile.</span><span class="sxs-lookup"><span data-stu-id="a52ac-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a52ac-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a52ac-121">Requirements</span></span>  
  
|<span data-ttu-id="a52ac-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a52ac-122">MOF</span></span>|<span data-ttu-id="a52ac-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a52ac-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a52ac-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a52ac-124">Namespace</span></span>|<span data-ttu-id="a52ac-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a52ac-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a52ac-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a52ac-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
