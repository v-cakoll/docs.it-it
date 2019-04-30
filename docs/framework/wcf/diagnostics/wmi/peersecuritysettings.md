---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 1c33e1ce710fea3b1698a6dab47a199e40388f5a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963007"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="1d6e5-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="1d6e5-102">PeerSecuritySettings</span></span>
<span data-ttu-id="1d6e5-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="1d6e5-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d6e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d6e5-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1d6e5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1d6e5-105">Methods</span></span>  
 <span data-ttu-id="1d6e5-106">La classe PeerSecuritySettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="1d6e5-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1d6e5-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1d6e5-107">Properties</span></span>  
 <span data-ttu-id="1d6e5-108">La classe PeerSecuritySettings ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d6e5-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="1d6e5-109">Modalità</span><span class="sxs-lookup"><span data-stu-id="1d6e5-109">Mode</span></span>  
 <span data-ttu-id="1d6e5-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="1d6e5-110">Data type: string</span></span>  
  
 <span data-ttu-id="1d6e5-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1d6e5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1d6e5-112">Se un endpoint configurato con l'associazione utilizza meccanismi di sicurezza a livello di messaggio o di trasporto.</span><span class="sxs-lookup"><span data-stu-id="1d6e5-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="1d6e5-113">Trasporto</span><span class="sxs-lookup"><span data-stu-id="1d6e5-113">Transport</span></span>  
 <span data-ttu-id="1d6e5-114">Tipo di dati: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="1d6e5-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="1d6e5-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1d6e5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1d6e5-116">Impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="1d6e5-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d6e5-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d6e5-117">Requirements</span></span>  
  
|<span data-ttu-id="1d6e5-118">MOF</span><span class="sxs-lookup"><span data-stu-id="1d6e5-118">MOF</span></span>|<span data-ttu-id="1d6e5-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1d6e5-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1d6e5-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="1d6e5-120">Namespace</span></span>|<span data-ttu-id="1d6e5-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1d6e5-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d6e5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d6e5-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
