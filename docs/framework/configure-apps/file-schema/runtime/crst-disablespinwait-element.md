---
title: Elemento <Crst_DisableSpinWait>
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 0683081183081e249b2a9c89e1a6a15f638fb339
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117646"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="4ccb2-102">Elemento \<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="4ccb2-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="4ccb2-103">Specifica se disabilitare lo spin-waiting per una sezione critica in caso di conflitto.</span><span class="sxs-lookup"><span data-stu-id="4ccb2-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="4ccb2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ccb2-104">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ccb2-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4ccb2-105">Attributes and Elements</span></span>

<span data-ttu-id="4ccb2-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4ccb2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ccb2-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ccb2-107">Attributes</span></span>  
  
|<span data-ttu-id="4ccb2-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="4ccb2-108">Attribute</span></span>|<span data-ttu-id="4ccb2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ccb2-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ccb2-110">**abilitato**</span><span class="sxs-lookup"><span data-stu-id="4ccb2-110">**enabled**</span></span>|<span data-ttu-id="4ccb2-111">Specifica se la rotazione in attesa di sezioni critiche quando sono in conflitto è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="4ccb2-111">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4ccb2-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="4ccb2-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="4ccb2-113">Valore</span><span class="sxs-lookup"><span data-stu-id="4ccb2-113">Value</span></span>|<span data-ttu-id="4ccb2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ccb2-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4ccb2-115">1</span><span class="sxs-lookup"><span data-stu-id="4ccb2-115">1</span></span>|<span data-ttu-id="4ccb2-116">Disabilitare la rotazione in attesa quando non è possibile acquisire una sezione critica.</span><span class="sxs-lookup"><span data-stu-id="4ccb2-116">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="4ccb2-117">0</span><span class="sxs-lookup"><span data-stu-id="4ccb2-117">0</span></span>|<span data-ttu-id="4ccb2-118">Non disabilitare la rotazione in attesa quando non è possibile acquisire una sezione critica.</span><span class="sxs-lookup"><span data-stu-id="4ccb2-118">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="4ccb2-119">Si tratta del valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4ccb2-119">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ccb2-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4ccb2-120">Child Elements</span></span>  
 <span data-ttu-id="4ccb2-121">No.</span><span class="sxs-lookup"><span data-stu-id="4ccb2-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ccb2-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4ccb2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4ccb2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ccb2-123">Element</span></span>|<span data-ttu-id="4ccb2-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ccb2-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4ccb2-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ccb2-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4ccb2-126">Contiene informazioni sulle varie impostazioni di configurazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="4ccb2-126">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4ccb2-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ccb2-127">Example</span></span>  

<span data-ttu-id="4ccb2-128">Nell'esempio seguente viene disabilitata la rotazione in attesa nelle sezioni critiche quando è in conflitto.</span><span class="sxs-lookup"><span data-stu-id="4ccb2-128">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ccb2-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4ccb2-129">See also</span></span>

- [<span data-ttu-id="4ccb2-130">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="4ccb2-130">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4ccb2-131">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="4ccb2-131">Configuration File Schema</span></span>](../index.md)
