---
title: 'Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico'
ms.date: 09/12/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9b9c9cbdb89ccf67942dcccee37ea410c6fa39a5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208672"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico

Quando si esegue la compilazione di App in Visual Studio che hanno come destinazione il [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] e versioni successive, i reindirizzamenti di associazione possono essere aggiunte automaticamente al file di configurazione dell'app per eseguire l'override di unificazione degli assembly. I reindirizzamenti di associazione vengono aggiunti se l'app o i relativi componenti fanno riferimento a più di una versione dello stesso assembly, anche se è possibile specificare manualmente i reindirizzamenti di associazione nel file di configurazione dell'app. La funzionalità di reindirizzamento di associazione automatico influisce sulle App web e App desktop tradizionali destinate le [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] o versione successiva, anche se il comportamento è leggermente diverso per un'app web. È possibile abilitare il reindirizzamento di associazione automatico se sono presenti app destinate alle versioni precedenti di .NET Framework o per mantenere i reindirizzamenti di associazione creati manualmente.

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a>Disabilitare i reindirizzamenti di associazione automatici nelle App desktop

I reindirizzamenti di associazione automatici sono abilitati per impostazione predefinita per le app desktop tradizionali destinate a [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] e versioni successive. I reindirizzamenti di associazione vengono aggiunti al file di configurazione di output (app.config) quando l'applicazione viene compilata ed eseguire l'override dell'unificazione degli assembly che in caso contrario potrebbe essere eseguito. Il file app.config di origine non viene modificato. È possibile disabilitare questa funzionalità modificando il file di progetto per l'app.

1. Aprire il file di progetto per la modifica mediante uno dei metodi seguenti:

   - In Visual Studio, selezionare il progetto in **Esplora soluzioni**, quindi scegliere **Apri cartella in Esplora File** dal menu di scelta rapida. In Esplora File, trovare il file di progetto (con estensione csproj o vbproj) e aprirlo con blocco note.
   - In Visual Studio, in **Esplora soluzioni**, fare clic sul progetto e scegliere **Scarica progetto**. Fare clic nuovamente sul progetto scaricato e quindi scegliere **modifica [NomeProgetto]**.

2. Nel file di progetto trovare la voce di proprietà seguente:

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. Modificare `true` in `false`:

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a>Abilitare manualmente reindirizzamenti di associazione automatici

È possibile abilitare reindirizzamenti di associazione automatici nelle App esistenti che destinate alle versioni precedenti di .NET Framework o nei casi in cui viene automaticamente richiesto di aggiungere un reindirizzamento. Se si ha come destinazione una versione più recente del framework, ma non automaticamente richiesto di aggiungere un reindirizzamento, probabilmente si otterrà output di compilazione che viene suggerito di che rimappare gli assembly.

1. Aprire il file di progetto per la modifica mediante uno dei metodi seguenti:

   - In Visual Studio, selezionare il progetto in **Esplora soluzioni**, quindi scegliere **Apri cartella in Esplora File** dal menu di scelta rapida. In Esplora File, trovare il file di progetto (con estensione csproj o vbproj) e aprirlo con blocco note.
   - In Visual Studio, in **Esplora soluzioni**, fare clic sul progetto e scegliere **Scarica progetto**. Fare clic nuovamente sul progetto scaricato e quindi scegliere **modifica [NomeProgetto]**.

2. Aggiungere l'elemento seguente al primo gruppo di proprietà di configurazione (sotto il \<PropertyGroup > tag):

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   Di seguito viene illustrato un esempio di file di progetto con l'elemento inserito:

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
       <PropertyGroup>
         <Configuration Condition=" '$(Configuration)' == ''     ">Debug</Configuration>
         <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
         <ProjectGuid>{123334}</ProjectGuid>
         ...
         <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
       </PropertyGroup>
     ...
   </Project>
   ```

3. Compilare l'app.

## <a name="enable-automatic-binding-redirects-in-web-apps"></a>Abilita reindirizzamenti di associazione automatici nelle App web

I reindirizzamenti di associazione automatici vengono implementati in modo diverso per le app Web. Poiché il file di configurazione di origine (web.config) deve essere modificato per le app Web, i reindirizzamenti di associazione non vengono aggiunti automaticamente al file di configurazione. Visual Studio notifica, tuttavia, eventuali conflitti di associazione ed è possibile aggiungere reindirizzamenti di associazione per risolverli. Poiché viene sempre chiesto aggiungere reindirizzamenti di associazione, non è necessario disabilitare in modo esplicito questa funzionalità per un'app web.

Per aggiungere reindirizzamenti di associazione in un file Web. config:

1. In Visual Studio compilare l'app e cercare eventuali avvisi di compilazione.

   ![Avviso di compilazione per conflitti di riferimenti all'assembly](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")

2. In caso di conflitti di associazione a livello di assembly, viene visualizzato un avviso. Fare doppio clic su avviso oppure selezionare l'avviso e premere **invio**.

   Verrà visualizzata una finestra di dialogo che consente di aggiungere automaticamente i reindirizzamenti di associazione necessari al file web.config di origine.

   ![Finestra di dialogo dell'autorizzazione reindirizzamento associazione](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")

## <a name="see-also"></a>Vedere anche

- [\<bindingRedirect > elemento](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [Reindirizzamento delle versioni di assembly](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
