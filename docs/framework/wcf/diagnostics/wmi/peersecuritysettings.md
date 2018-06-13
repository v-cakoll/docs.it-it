---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 58b372f26fee7dc180d75731fd4855db569c87c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484521"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="f37e6-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f37e6-102">PeerSecuritySettings</span></span>
<span data-ttu-id="f37e6-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f37e6-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f37e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f37e6-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f37e6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f37e6-105">Methods</span></span>  
 <span data-ttu-id="f37e6-106">La classe PeerSecuritySettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="f37e6-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f37e6-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f37e6-107">Properties</span></span>  
 <span data-ttu-id="f37e6-108">La classe PeerSecuritySettings ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="f37e6-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="f37e6-109">Modalità</span><span class="sxs-lookup"><span data-stu-id="f37e6-109">Mode</span></span>  
 <span data-ttu-id="f37e6-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="f37e6-110">Data type: string</span></span>  
  
 <span data-ttu-id="f37e6-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f37e6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f37e6-112">Se un endpoint configurato con l'associazione utilizza meccanismi di sicurezza a livello di messaggio o di trasporto.</span><span class="sxs-lookup"><span data-stu-id="f37e6-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="f37e6-113">Trasporto</span><span class="sxs-lookup"><span data-stu-id="f37e6-113">Transport</span></span>  
 <span data-ttu-id="f37e6-114">Tipo di dati: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f37e6-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="f37e6-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f37e6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f37e6-116">Impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="f37e6-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f37e6-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f37e6-117">Requirements</span></span>  
  
|<span data-ttu-id="f37e6-118">MOF</span><span class="sxs-lookup"><span data-stu-id="f37e6-118">MOF</span></span>|<span data-ttu-id="f37e6-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f37e6-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f37e6-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="f37e6-120">Namespace</span></span>|<span data-ttu-id="f37e6-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f37e6-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f37e6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f37e6-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
