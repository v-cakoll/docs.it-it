---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
author: BrucePerlerMS
ms.openlocfilehash: 19c65b3028ad63b8a78205d00f44cc32322648d5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47396848"
---
# <a name="securitybindingelement"></a><span data-ttu-id="a2ea6-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a2ea6-102">SecurityBindingElement</span></span>
<span data-ttu-id="a2ea6-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a2ea6-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2ea6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2ea6-104">Syntax</span></span>  
  
```  
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a2ea6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a2ea6-105">Methods</span></span>  
 <span data-ttu-id="a2ea6-106">La classe SecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a2ea6-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a2ea6-107">Properties</span></span>  
 <span data-ttu-id="a2ea6-108">La classe SecurityBindingElement ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2ea6-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="a2ea6-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="a2ea6-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="a2ea6-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a2ea6-110">Data type: string</span></span>  
  
 <span data-ttu-id="a2ea6-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a2ea6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2ea6-112">Specifica gli algoritmi da usare con l'associazione.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="a2ea6-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="a2ea6-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="a2ea6-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="a2ea6-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="a2ea6-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a2ea6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2ea6-116">Valore booleano che specifica se ogni messaggio contiene un timestamp.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="a2ea6-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="a2ea6-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="a2ea6-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a2ea6-118">Data type: string</span></span>  
  
 <span data-ttu-id="a2ea6-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a2ea6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2ea6-120">Origine dell'entropia usata per creare chiavi.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="a2ea6-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="a2ea6-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="a2ea6-122">Tipo di dati: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="a2ea6-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="a2ea6-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a2ea6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2ea6-124">Proprietà di sicurezza specifiche dell'associazione per il servizio locale.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="a2ea6-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="a2ea6-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="a2ea6-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a2ea6-126">Data type: string</span></span>  
  
 <span data-ttu-id="a2ea6-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a2ea6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2ea6-128">Versione usata per la protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="a2ea6-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="a2ea6-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="a2ea6-130">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a2ea6-130">Data type: string</span></span>  
  
 <span data-ttu-id="a2ea6-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a2ea6-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2ea6-132">Ordine degli elementi nell'intestazione di sicurezza di questa associazione.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2ea6-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2ea6-133">Requirements</span></span>  
  
|<span data-ttu-id="a2ea6-134">MOF</span><span class="sxs-lookup"><span data-stu-id="a2ea6-134">MOF</span></span>|<span data-ttu-id="a2ea6-135">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a2ea6-136">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a2ea6-136">Namespace</span></span>|<span data-ttu-id="a2ea6-137">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a2ea6-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2ea6-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2ea6-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
