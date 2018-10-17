---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373996"
---
# <a name="wsattracerecord"></a><span data-ttu-id="cf99a-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="cf99a-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="cf99a-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="cf99a-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf99a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf99a-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cf99a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="cf99a-105">Methods</span></span>  
 <span data-ttu-id="cf99a-106">La classe WSAT_TraceRecord non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="cf99a-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cf99a-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cf99a-107">Properties</span></span>  
 <span data-ttu-id="cf99a-108">La classe WSAT_TraceRecord dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf99a-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="cf99a-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="cf99a-109">ActivityID</span></span>  
 <span data-ttu-id="cf99a-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="cf99a-110">Data type: object</span></span>  
<span data-ttu-id="cf99a-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="cf99a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf99a-112">ID attività del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="cf99a-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="cf99a-113">ID evento</span><span class="sxs-lookup"><span data-stu-id="cf99a-113">EventID</span></span>  
 <span data-ttu-id="cf99a-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="cf99a-114">Data type: sint32</span></span>  
<span data-ttu-id="cf99a-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="cf99a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf99a-116">ID evento del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="cf99a-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="cf99a-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="cf99a-117">TraceRecord</span></span>  
 <span data-ttu-id="cf99a-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="cf99a-118">Data type: string</span></span>  
<span data-ttu-id="cf99a-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="cf99a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf99a-120">Record di traccia</span><span class="sxs-lookup"><span data-stu-id="cf99a-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf99a-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf99a-121">Requirements</span></span>  
  
|<span data-ttu-id="cf99a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="cf99a-122">MOF</span></span>|<span data-ttu-id="cf99a-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cf99a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cf99a-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="cf99a-124">Namespace</span></span>|<span data-ttu-id="cf99a-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cf99a-125">Defined in root\ServiceModel</span></span>|
