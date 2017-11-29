---
title: Schema delle sezioni di configurazione
ms.date: 05/02/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c668cf3d2f2c0bcffda185cea01edfb9e55c6d6c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="829e0-102">Schema delle sezioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="829e0-102">Configuration sections schema</span></span>

<span data-ttu-id="829e0-103">Lo schema di sezioni di configurazione contiene elementi che definiscono le impostazioni personalizzate nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="829e0-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="829e0-104">Per informazioni generali sui file di configurazione e gli schemi, vedere [schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="829e0-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="829e0-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="829e0-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="829e0-106">[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="829e0-106">[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="829e0-107">[**\<Deselezionare >**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="829e0-107">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="829e0-108">[**\<rimuovere >**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="829e0-108">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="829e0-109">[**\<sezione >**](~/docs/framework/configure-apps/file-schema/section-element.md) </span><span class="sxs-lookup"><span data-stu-id="829e0-109">[**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) </span></span>  
[<span data-ttu-id="829e0-110">**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="829e0-110">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="829e0-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="829e0-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="829e0-112">**\<Deselezionare >** per  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="829e0-112">**\<clear>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="829e0-113">Cancella tutte le sezioni definite in precedenza e i gruppi di sezioni.</span><span class="sxs-lookup"><span data-stu-id="829e0-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="829e0-114">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="829e0-114">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="829e0-115">Cancella tutte le sezioni definite in precedenza e i gruppi di sezioni.</span><span class="sxs-lookup"><span data-stu-id="829e0-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="829e0-116">**\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="829e0-116">**\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="829e0-117">Contiene le dichiarazioni dello spazio dei nomi e di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="829e0-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="829e0-118">**\<rimuovere >** per  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="829e0-118">**\<remove>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="829e0-119">Rimuove una sezione predefinita o il gruppo di sezione.</span><span class="sxs-lookup"><span data-stu-id="829e0-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="829e0-120">**\<sezione >** per  **\<configSections >** e  **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="829e0-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="829e0-121">Contiene una dichiarazione di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="829e0-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="829e0-122">**\<sectionGroup >** per  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="829e0-122">**\<sectionGroup>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="829e0-123">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="829e0-123">Defines a namespace for configuration sections.</span></span> |
