---
title: <legacyCorruptedStateExceptionsPolicy> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: d1d29a37999a01f3e370897a1052f4f94435a218
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116463"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="642d6-102">\<legacyCorruptedStateExceptionsPolicy> Elemento</span><span class="sxs-lookup"><span data-stu-id="642d6-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="642d6-103">Specifica se il Common Language Runtime consente al codice gestito di intercettare le violazioni di accesso e altre eccezioni di stato danneggiate.</span><span class="sxs-lookup"><span data-stu-id="642d6-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="642d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="642d6-104">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="642d6-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="642d6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="642d6-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="642d6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="642d6-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="642d6-107">Attributes</span></span>  
  
|<span data-ttu-id="642d6-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="642d6-108">Attribute</span></span>|<span data-ttu-id="642d6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="642d6-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="642d6-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="642d6-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="642d6-111">Specifica che l'applicazione rileverà gli errori di eccezioni di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="642d6-111">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="642d6-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="642d6-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="642d6-113">Valore</span><span class="sxs-lookup"><span data-stu-id="642d6-113">Value</span></span>|<span data-ttu-id="642d6-114">Description</span><span class="sxs-lookup"><span data-stu-id="642d6-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="642d6-115">L'applicazione non rileverà gli errori di eccezione di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="642d6-115">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="642d6-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="642d6-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="642d6-117">L'applicazione rileverà gli errori di eccezioni di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="642d6-117">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="642d6-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="642d6-118">Child Elements</span></span>  
 <span data-ttu-id="642d6-119">No.</span><span class="sxs-lookup"><span data-stu-id="642d6-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="642d6-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="642d6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="642d6-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="642d6-121">Element</span></span>|<span data-ttu-id="642d6-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="642d6-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="642d6-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="642d6-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="642d6-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="642d6-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="642d6-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="642d6-125">Remarks</span></span>  
 <span data-ttu-id="642d6-126">Nel .NET Framework versione 3,5 e versioni precedenti, il Common Language Runtime codice gestito consentito per intercettare le eccezioni generate da Stati di processo danneggiati.</span><span class="sxs-lookup"><span data-stu-id="642d6-126">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="642d6-127">Una violazione di accesso è un esempio di questo tipo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="642d6-127">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="642d6-128">A partire da .NET Framework 4, il codice gestito non rileva più questi tipi di eccezioni nei `catch` blocchi.</span><span class="sxs-lookup"><span data-stu-id="642d6-128">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="642d6-129">Tuttavia, è possibile eseguire l'override di questa modifica e mantenere la gestione delle eccezioni di stato danneggiate in due modi:</span><span class="sxs-lookup"><span data-stu-id="642d6-129">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="642d6-130">Impostare l' `<legacyCorruptedStateExceptionsPolicy>` attributo dell'elemento `enabled` su `true` .</span><span class="sxs-lookup"><span data-stu-id="642d6-130">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="642d6-131">Questa impostazione di configurazione viene applicata processwide e influiscono su tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="642d6-131">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="642d6-132">-oppure-</span><span class="sxs-lookup"><span data-stu-id="642d6-132">-or-</span></span>  
  
- <span data-ttu-id="642d6-133">Applicare l' <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attributo al metodo che contiene il blocco Exceptions `catch` .</span><span class="sxs-lookup"><span data-stu-id="642d6-133">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="642d6-134">Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="642d6-134">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="642d6-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="642d6-135">Example</span></span>  
 <span data-ttu-id="642d6-136">Nell'esempio seguente viene illustrato come specificare che l'applicazione deve ripristinare il comportamento prima del .NET Framework 4 e rilevare tutti gli errori di eccezioni di stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="642d6-136">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="642d6-137">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="642d6-137">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="642d6-138">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="642d6-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="642d6-139">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="642d6-139">Configuration File Schema</span></span>](../index.md)
