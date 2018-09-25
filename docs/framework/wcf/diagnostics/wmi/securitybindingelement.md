---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
author: BrucePerlerMS
ms.openlocfilehash: 19c65b3028ad63b8a78205d00f44cc32322648d5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47069974"
---
# <a name="securitybindingelement"></a><span data-ttu-id="7ae31-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="7ae31-102">SecurityBindingElement</span></span>
<span data-ttu-id="7ae31-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="7ae31-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ae31-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="7ae31-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7ae31-105">Methods</span></span>  
 <span data-ttu-id="7ae31-106">La classe SecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="7ae31-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7ae31-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7ae31-107">Properties</span></span>  
 <span data-ttu-id="7ae31-108">La classe SecurityBindingElement ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ae31-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="7ae31-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="7ae31-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="7ae31-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="7ae31-110">Data type: string</span></span>  
  
 <span data-ttu-id="7ae31-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="7ae31-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ae31-112">Specifica gli algoritmi da usare con l'associazione.</span><span class="sxs-lookup"><span data-stu-id="7ae31-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="7ae31-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="7ae31-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="7ae31-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="7ae31-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="7ae31-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="7ae31-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ae31-116">Valore booleano che specifica se ogni messaggio contiene un timestamp.</span><span class="sxs-lookup"><span data-stu-id="7ae31-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="7ae31-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="7ae31-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="7ae31-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="7ae31-118">Data type: string</span></span>  
  
 <span data-ttu-id="7ae31-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="7ae31-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ae31-120">Origine dell'entropia usata per creare chiavi.</span><span class="sxs-lookup"><span data-stu-id="7ae31-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="7ae31-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="7ae31-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="7ae31-122">Tipo di dati: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="7ae31-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="7ae31-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="7ae31-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ae31-124">Proprietà di sicurezza specifiche dell'associazione per il servizio locale.</span><span class="sxs-lookup"><span data-stu-id="7ae31-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="7ae31-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="7ae31-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="7ae31-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="7ae31-126">Data type: string</span></span>  
  
 <span data-ttu-id="7ae31-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="7ae31-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ae31-128">Versione usata per la protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="7ae31-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="7ae31-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="7ae31-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="7ae31-130">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="7ae31-130">Data type: string</span></span>  
  
 <span data-ttu-id="7ae31-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="7ae31-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ae31-132">Ordine degli elementi nell'intestazione di sicurezza di questa associazione.</span><span class="sxs-lookup"><span data-stu-id="7ae31-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ae31-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ae31-133">Requirements</span></span>  
  
|<span data-ttu-id="7ae31-134">MOF</span><span class="sxs-lookup"><span data-stu-id="7ae31-134">MOF</span></span>|<span data-ttu-id="7ae31-135">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7ae31-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7ae31-136">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="7ae31-136">Namespace</span></span>|<span data-ttu-id="7ae31-137">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7ae31-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ae31-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ae31-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
