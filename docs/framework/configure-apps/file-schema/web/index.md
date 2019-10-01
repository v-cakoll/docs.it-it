---
title: Schema delle impostazioni Web
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
ms.openlocfilehash: 71b9e46a8c2d60c853af63ee78e2ed5dbe6e98f4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699143"
---
# <a name="web-settings-schema"></a><span data-ttu-id="b1270-102">Schema delle impostazioni Web</span><span class="sxs-lookup"><span data-stu-id="b1270-102">Web Settings Schema</span></span>
<span data-ttu-id="b1270-103">Le impostazioni Web specificano le impostazioni di ASP.NET a livello di CPU e di esecuzione che si applicano al comportamento a livello di processo gestito dal livello di hosting ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b1270-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="b1270-104">Queste impostazioni differiscono dalle impostazioni di tipo dominio dell'applicazione specificate nel file Web.config di un'applicazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b1270-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="b1270-105">Le impostazioni Web sono contenute nei file Aspnet.config, disponibili nelle cartelle di installazione per le versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b1270-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="b1270-106">Il file Aspnet. config per .NET Framework 2,0, ad esempio, si trova nella cartella seguente:</span><span class="sxs-lookup"><span data-stu-id="b1270-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="b1270-107">Le impostazioni Web non vengono usate in altri file di configurazione, ad esempio il file machine.config, il file Web.config radice o i file Web.config a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1270-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
[<span data-ttu-id="b1270-108"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b1270-108">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b1270-109">&nbsp; @ no__t-1[ **@no__t -4system. Web >** ](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b1270-109">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="b1270-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<applicationPool >** ](applicationpool-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b1270-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)</span></span>  
  
|<span data-ttu-id="b1270-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1270-111">Element</span></span>|<span data-ttu-id="b1270-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1270-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1270-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="b1270-113">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="b1270-114">Contiene informazioni usate dal livello di hosting ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b1270-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="b1270-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="b1270-115">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="b1270-116">Specifica le impostazioni di ASP.NET a livello di CPU e di esecuzione che si applicano al comportamento a livello di processo gestito dal livello di hosting ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b1270-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1270-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1270-117">See also</span></span>

- [<span data-ttu-id="b1270-118">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b1270-118">Configuration File Schema</span></span>](../index.md)
