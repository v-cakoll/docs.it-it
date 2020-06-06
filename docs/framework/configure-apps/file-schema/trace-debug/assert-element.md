---
title: <assert> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: f3c1a1670139a8262dea449bfff99c7c1c19f088
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088940"
---
# <a name="assert-element"></a><span data-ttu-id="4c0a3-102">\<assert> Elemento</span><span class="sxs-lookup"><span data-stu-id="4c0a3-102">\<assert> Element</span></span>
<span data-ttu-id="4c0a3-103">Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**

## <a name="syntax"></a><span data-ttu-id="4c0a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c0a3-104">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c0a3-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4c0a3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4c0a3-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c0a3-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="4c0a3-107">Attributes</span></span>  
  
|<span data-ttu-id="4c0a3-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="4c0a3-108">Attribute</span></span>|<span data-ttu-id="4c0a3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c0a3-109">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="4c0a3-110">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4c0a3-111">Specifica se visualizzare una finestra di messaggio quando il metodo **debug. Assert** restituisce **false**.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-111">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="4c0a3-112">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4c0a3-113">Specifica il nome del file in cui scrivere il messaggio se **debug. Assert** restituisce **false**.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-113">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="4c0a3-114">Attributo AssertUiEnabled</span><span class="sxs-lookup"><span data-stu-id="4c0a3-114">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="4c0a3-115">Valore</span><span class="sxs-lookup"><span data-stu-id="4c0a3-115">Value</span></span>|<span data-ttu-id="4c0a3-116">Description</span><span class="sxs-lookup"><span data-stu-id="4c0a3-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="4c0a3-117">Consente di visualizzare la finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-117">Displays the message box.</span></span> <span data-ttu-id="4c0a3-118">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="4c0a3-119">La finestra di messaggio non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-119">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c0a3-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4c0a3-120">Child Elements</span></span>  
 <span data-ttu-id="4c0a3-121">No.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c0a3-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4c0a3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4c0a3-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c0a3-123">Element</span></span>|<span data-ttu-id="4c0a3-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c0a3-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4c0a3-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4c0a3-126">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c0a3-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="4c0a3-127">Remarks</span></span>  
 <span data-ttu-id="4c0a3-128">Entrambi gli attributi nell' **\<assert>** elemento sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-128">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="4c0a3-129">È possibile disabilitare le finestre di messaggio senza specificare un file in cui scrivere i messaggi. in alternativa, è possibile specificare un file in cui scrivere i messaggi lasciando abilitate le finestre di messaggio.</span><span class="sxs-lookup"><span data-stu-id="4c0a3-129">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c0a3-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c0a3-130">Example</span></span>  
 <span data-ttu-id="4c0a3-131">Nell'esempio seguente viene illustrato come disabilitare la visualizzazione di finestre di messaggio quando si chiama **debug. Assert** e si scrivono i messaggi in `c:\log.txt` .</span><span class="sxs-lookup"><span data-stu-id="4c0a3-131">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c0a3-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4c0a3-132">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="4c0a3-133">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="4c0a3-133">Trace and Debug Settings Schema</span></span>](index.md)
