---
title: "&lt;l'asserzione&gt; elemento"
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b15e569ff6e42298c0a1de02f77ab7c302c70d86
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154242"
---
# <a name="ltassertgt-element"></a><span data-ttu-id="cca28-102">&lt;l'asserzione&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="cca28-102">&lt;assert&gt; Element</span></span>
<span data-ttu-id="cca28-103">Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="cca28-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="cca28-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cca28-104">\<configuration></span></span>  
<span data-ttu-id="cca28-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="cca28-105">\<system.diagnostics></span></span>  
<span data-ttu-id="cca28-106">\<Assert ></span><span class="sxs-lookup"><span data-stu-id="cca28-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca28-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cca28-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cca28-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cca28-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cca28-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cca28-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cca28-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="cca28-110">Attributes</span></span>  
  
|<span data-ttu-id="cca28-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="cca28-111">Attribute</span></span>|<span data-ttu-id="cca28-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cca28-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="cca28-113">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cca28-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="cca28-114">Specifica se visualizzare un finestra di messaggio quando il **debug. Assert** metodo restituisca **false**.</span><span class="sxs-lookup"><span data-stu-id="cca28-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="cca28-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cca28-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="cca28-116">Specifica il nome del file in cui scrivere il messaggio se **debug. Assert** restituisca **false**.</span><span class="sxs-lookup"><span data-stu-id="cca28-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="cca28-117">Attributo AssertUiEnabled</span><span class="sxs-lookup"><span data-stu-id="cca28-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="cca28-118">Value</span><span class="sxs-lookup"><span data-stu-id="cca28-118">Value</span></span>|<span data-ttu-id="cca28-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cca28-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="cca28-120">Consente di visualizzare la finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="cca28-120">Displays the message box.</span></span> <span data-ttu-id="cca28-121">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cca28-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="cca28-122">Non viene visualizzata la finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="cca28-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cca28-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cca28-123">Child Elements</span></span>  
 <span data-ttu-id="cca28-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cca28-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cca28-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cca28-125">Parent Elements</span></span>  
  
|<span data-ttu-id="cca28-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="cca28-126">Element</span></span>|<span data-ttu-id="cca28-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cca28-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cca28-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cca28-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="cca28-129">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="cca28-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cca28-130">Note</span><span class="sxs-lookup"><span data-stu-id="cca28-130">Remarks</span></span>  
 <span data-ttu-id="cca28-131">Entrambi gli attributi di  **\<assert >** elemento sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="cca28-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="cca28-132">È possibile disabilitare le finestre di messaggio senza specificare un file in cui scrivere i messaggi da, o è possibile specificare un file in cui scrivere lasciando le finestre di messaggio abilitate.</span><span class="sxs-lookup"><span data-stu-id="cca28-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cca28-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="cca28-133">Example</span></span>  
 <span data-ttu-id="cca28-134">Nell'esempio seguente viene illustrato come disabilitare la visualizzazione di finestre di messaggio quando si chiama **debug. Assert** e scrivere i messaggi da `c:\log.txt`.</span><span class="sxs-lookup"><span data-stu-id="cca28-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cca28-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cca28-135">See Also</span></span>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="cca28-136">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="cca28-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
