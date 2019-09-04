---
title: <legacyCorruptedStateExceptionsPolicy> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6566437d899b768cda1bab74bb1310deb7aa74db
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252509"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="235c8-102">\<Elemento > legacyCorruptedStateExceptionsPolicy</span><span class="sxs-lookup"><span data-stu-id="235c8-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="235c8-103">Specifica se il Common Language Runtime consente al codice gestito di intercettare le violazioni di accesso e altre eccezioni di stato danneggiate.</span><span class="sxs-lookup"><span data-stu-id="235c8-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
<span data-ttu-id="235c8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="235c8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="235c8-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="235c8-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="235c8-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<legacyCorruptedStateExceptionsPolicy>**</span><span class="sxs-lookup"><span data-stu-id="235c8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="235c8-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="235c8-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="235c8-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="235c8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="235c8-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="235c8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="235c8-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="235c8-110">Attributes</span></span>  
  
|<span data-ttu-id="235c8-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="235c8-111">Attribute</span></span>|<span data-ttu-id="235c8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="235c8-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="235c8-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="235c8-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="235c8-114">Specifica che l'applicazione rileverà gli errori di eccezioni di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="235c8-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="235c8-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="235c8-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="235c8-116">Valore</span><span class="sxs-lookup"><span data-stu-id="235c8-116">Value</span></span>|<span data-ttu-id="235c8-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="235c8-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="235c8-118">L'applicazione non rileverà gli errori di eccezione di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="235c8-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="235c8-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="235c8-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="235c8-120">L'applicazione rileverà gli errori di eccezioni di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="235c8-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="235c8-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="235c8-121">Child Elements</span></span>  
 <span data-ttu-id="235c8-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="235c8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="235c8-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="235c8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="235c8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="235c8-124">Element</span></span>|<span data-ttu-id="235c8-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="235c8-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="235c8-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="235c8-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="235c8-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="235c8-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="235c8-128">Note</span><span class="sxs-lookup"><span data-stu-id="235c8-128">Remarks</span></span>  
 <span data-ttu-id="235c8-129">Nel .NET Framework versione 3,5 e versioni precedenti, il Common Language Runtime codice gestito consentito per intercettare le eccezioni generate da Stati di processo danneggiati.</span><span class="sxs-lookup"><span data-stu-id="235c8-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="235c8-130">Una violazione di accesso è un esempio di questo tipo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="235c8-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="235c8-131">A partire da .NET Framework 4, il codice gestito non rileva più questi tipi di eccezioni nei `catch` blocchi.</span><span class="sxs-lookup"><span data-stu-id="235c8-131">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="235c8-132">Tuttavia, è possibile eseguire l'override di questa modifica e mantenere la gestione delle eccezioni di stato danneggiate in due modi:</span><span class="sxs-lookup"><span data-stu-id="235c8-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="235c8-133">Impostare l' `<legacyCorruptedStateExceptionsPolicy>` `enabled` attributo dell'elemento su `true`.</span><span class="sxs-lookup"><span data-stu-id="235c8-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="235c8-134">Questa impostazione di configurazione viene applicata processwide e influiscono su tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="235c8-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="235c8-135">-oppure-</span><span class="sxs-lookup"><span data-stu-id="235c8-135">-or-</span></span>  
  
- <span data-ttu-id="235c8-136">Applicare l' <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attributo al metodo che contiene il blocco Exceptions `catch` .</span><span class="sxs-lookup"><span data-stu-id="235c8-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="235c8-137">Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="235c8-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="235c8-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="235c8-138">Example</span></span>  
 <span data-ttu-id="235c8-139">Nell'esempio seguente viene illustrato come specificare che l'applicazione deve ripristinare il comportamento prima del .NET Framework 4 e rilevare tutti gli errori di eccezioni di stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="235c8-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="235c8-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="235c8-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="235c8-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="235c8-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="235c8-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="235c8-142">Configuration File Schema</span></span>](../index.md)
