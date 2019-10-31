---
title: <legacyCorruptedStateExceptionsPolicy> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: d1d29a37999a01f3e370897a1052f4f94435a218
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116463"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="0d087-102">\<elemento > legacyCorruptedStateExceptionsPolicy</span><span class="sxs-lookup"><span data-stu-id="0d087-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="0d087-103">Specifica se il Common Language Runtime consente al codice gestito di intercettare le violazioni di accesso e altre eccezioni di stato danneggiate.</span><span class="sxs-lookup"><span data-stu-id="0d087-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
<span data-ttu-id="0d087-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0d087-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0d087-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="0d087-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="0d087-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<legacyCorruptedStateExceptionsPolicy >**</span><span class="sxs-lookup"><span data-stu-id="0d087-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d087-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d087-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d087-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0d087-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0d087-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0d087-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d087-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="0d087-110">Attributes</span></span>  
  
|<span data-ttu-id="0d087-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="0d087-111">Attribute</span></span>|<span data-ttu-id="0d087-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d087-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0d087-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0d087-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0d087-114">Specifica che l'applicazione rileverà gli errori di eccezioni di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="0d087-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0d087-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="0d087-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="0d087-116">Value</span><span class="sxs-lookup"><span data-stu-id="0d087-116">Value</span></span>|<span data-ttu-id="0d087-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d087-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0d087-118">L'applicazione non rileverà gli errori di eccezione di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="0d087-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="0d087-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0d087-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="0d087-120">L'applicazione rileverà gli errori di eccezioni di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="0d087-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d087-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0d087-121">Child Elements</span></span>  
 <span data-ttu-id="0d087-122">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="0d087-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d087-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0d087-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0d087-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d087-124">Element</span></span>|<span data-ttu-id="0d087-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d087-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0d087-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0d087-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0d087-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0d087-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d087-128">Note</span><span class="sxs-lookup"><span data-stu-id="0d087-128">Remarks</span></span>  
 <span data-ttu-id="0d087-129">Nel .NET Framework versione 3,5 e versioni precedenti, il Common Language Runtime codice gestito consentito per intercettare le eccezioni generate da Stati di processo danneggiati.</span><span class="sxs-lookup"><span data-stu-id="0d087-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="0d087-130">Una violazione di accesso è un esempio di questo tipo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="0d087-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="0d087-131">A partire da .NET Framework 4, il codice gestito non rileva più questi tipi di eccezioni nei blocchi di `catch`.</span><span class="sxs-lookup"><span data-stu-id="0d087-131">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="0d087-132">Tuttavia, è possibile eseguire l'override di questa modifica e mantenere la gestione delle eccezioni di stato danneggiate in due modi:</span><span class="sxs-lookup"><span data-stu-id="0d087-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="0d087-133">Impostare l'attributo `enabled` dell'elemento `<legacyCorruptedStateExceptionsPolicy>` su `true`.</span><span class="sxs-lookup"><span data-stu-id="0d087-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="0d087-134">Questa impostazione di configurazione viene applicata processwide e influiscono su tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="0d087-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="0d087-135">oppure</span><span class="sxs-lookup"><span data-stu-id="0d087-135">-or-</span></span>  
  
- <span data-ttu-id="0d087-136">Applicare l'attributo <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> al metodo che contiene le eccezioni `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="0d087-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="0d087-137">Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0d087-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d087-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d087-138">Example</span></span>  
 <span data-ttu-id="0d087-139">Nell'esempio seguente viene illustrato come specificare che l'applicazione deve ripristinare il comportamento prima del .NET Framework 4 e rilevare tutti gli errori di eccezioni di stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="0d087-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d087-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d087-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="0d087-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="0d087-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0d087-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0d087-142">Configuration File Schema</span></span>](../index.md)
