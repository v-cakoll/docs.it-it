---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8c2d4bfc08a503a8d6eb0e8abf6f1e798b90bc83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963215"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="1bdb2-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1bdb2-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="1bdb2-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1bdb2-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bdb2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bdb2-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1bdb2-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1bdb2-105">Methods</span></span>  
 <span data-ttu-id="1bdb2-106">La classe NamedPipeConnectionPoolSettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1bdb2-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1bdb2-107">Properties</span></span>  
 <span data-ttu-id="1bdb2-108">La classe NamedPipeConnectionPoolSettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bdb2-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="1bdb2-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="1bdb2-109">GroupName</span></span>  
 <span data-ttu-id="1bdb2-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="1bdb2-110">Data type: string</span></span>  
  
 <span data-ttu-id="1bdb2-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1bdb2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1bdb2-112">Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="1bdb2-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="1bdb2-113">IdleTimeout</span></span>  
 <span data-ttu-id="1bdb2-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="1bdb2-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="1bdb2-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1bdb2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1bdb2-116">Periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="1bdb2-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="1bdb2-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="1bdb2-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="1bdb2-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="1bdb2-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1bdb2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1bdb2-120">Numero massimo di connessioni in uscita per ogni endpoint sul client.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bdb2-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1bdb2-121">Requirements</span></span>  
  
|<span data-ttu-id="1bdb2-122">MOF</span><span class="sxs-lookup"><span data-stu-id="1bdb2-122">MOF</span></span>|<span data-ttu-id="1bdb2-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1bdb2-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1bdb2-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="1bdb2-124">Namespace</span></span>|<span data-ttu-id="1bdb2-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1bdb2-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bdb2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bdb2-126">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
