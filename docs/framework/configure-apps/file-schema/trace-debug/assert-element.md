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
ms.openlocfilehash: 30ec24aefcf8c4d1e110238a2c60a958eded5545
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699393"
---
# <a name="assert-element"></a><span data-ttu-id="61db8-102">Elemento > \<assert</span><span class="sxs-lookup"><span data-stu-id="61db8-102">\<assert> Element</span></span>
<span data-ttu-id="61db8-103">Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="61db8-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
[<span data-ttu-id="61db8-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="61db8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="61db8-105">&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="61db8-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="61db8-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<assert >**</span><span class="sxs-lookup"><span data-stu-id="61db8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61db8-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61db8-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61db8-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="61db8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="61db8-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="61db8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61db8-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="61db8-110">Attributes</span></span>  
  
|<span data-ttu-id="61db8-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="61db8-111">Attribute</span></span>|<span data-ttu-id="61db8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61db8-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="61db8-113">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="61db8-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="61db8-114">Specifica se visualizzare una finestra di messaggio quando il metodo **debug. Assert** restituisce **false**.</span><span class="sxs-lookup"><span data-stu-id="61db8-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="61db8-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="61db8-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="61db8-116">Specifica il nome del file in cui scrivere il messaggio se **debug. Assert** restituisce **false**.</span><span class="sxs-lookup"><span data-stu-id="61db8-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="61db8-117">Attributo AssertUiEnabled</span><span class="sxs-lookup"><span data-stu-id="61db8-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="61db8-118">Value</span><span class="sxs-lookup"><span data-stu-id="61db8-118">Value</span></span>|<span data-ttu-id="61db8-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61db8-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="61db8-120">Consente di visualizzare la finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="61db8-120">Displays the message box.</span></span> <span data-ttu-id="61db8-121">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="61db8-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="61db8-122">La finestra di messaggio non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="61db8-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61db8-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="61db8-123">Child Elements</span></span>  
 <span data-ttu-id="61db8-124">No.</span><span class="sxs-lookup"><span data-stu-id="61db8-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61db8-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="61db8-125">Parent Elements</span></span>  
  
|<span data-ttu-id="61db8-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="61db8-126">Element</span></span>|<span data-ttu-id="61db8-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61db8-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="61db8-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="61db8-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="61db8-129">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="61db8-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61db8-130">Note</span><span class="sxs-lookup"><span data-stu-id="61db8-130">Remarks</span></span>  
 <span data-ttu-id="61db8-131">Entrambi gli attributi nell'elemento **> \<assert** sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="61db8-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="61db8-132">È possibile disabilitare le finestre di messaggio senza specificare un file in cui scrivere i messaggi. in alternativa, è possibile specificare un file in cui scrivere i messaggi lasciando abilitate le finestre di messaggio.</span><span class="sxs-lookup"><span data-stu-id="61db8-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61db8-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="61db8-133">Example</span></span>  
 <span data-ttu-id="61db8-134">Nell'esempio seguente viene illustrato come disabilitare la visualizzazione di finestre di messaggio quando si chiama **debug. Assert** e si scrivono i messaggi in `c:\log.txt`.</span><span class="sxs-lookup"><span data-stu-id="61db8-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61db8-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61db8-135">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="61db8-136">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="61db8-136">Trace and Debug Settings Schema</span></span>](index.md)
