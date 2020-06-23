---
title: Abilitare o disabilitare i reindirizzamenti di binding generati automaticamente
description: Vedere come abilitare o disabilitare il reindirizzamento di associazione automatico. Questa funzionalità influiscono sulle app desktop e sulle app Web destinate a .NET 4.5.1 o versione successiva.
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: edee95f6c3b2c2d74c4f1b68e0a65e5cb0e85f54
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105385"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>Procedura: Abilitare e disabilitare il reindirizzamento di associazione automatico

Quando si compilano app in Visual Studio destinate a .NET Framework 4.5.1 e versioni successive, i reindirizzamenti di associazione possono essere aggiunti automaticamente al file di configurazione dell'app per eseguire l'override dell'unificazione degli assembly. I reindirizzamenti di associazione vengono aggiunti se l'app o i relativi componenti fanno riferimento a più di una versione dello stesso assembly, anche se è possibile specificare manualmente i reindirizzamenti di associazione nel file di configurazione dell'app. La funzionalità di reindirizzamento automatico dell'associazione influiscono sulle app desktop e sulle app Web destinate a .NET Framework 4.5.1 o versione successiva, anche se il comportamento è leggermente diverso per un'app Web. È possibile abilitare il reindirizzamento di associazione automatico se sono presenti app destinate a versioni precedenti del .NET Framework. in alternativa, è possibile disabilitare questa funzionalità se si desidera creare manualmente i reindirizzamenti di binding.

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a>Disabilitare i reindirizzamenti di binding automatici nelle app desktop

I reindirizzamenti di binding automatici sono abilitati per impostazione predefinita per le app desktop di Windows destinate a .NET Framework 4.5.1 e versioni successive. I reindirizzamenti di binding vengono aggiunti al file di configurazione di output (**app.config**) quando l'app viene compilata ed esegue l'override dell'unificazione di assembly che altrimenti potrebbe essere eseguita. Il file di **app.config** di origine non viene modificato. È possibile disabilitare questa funzionalità modificando il file di progetto per l'app o deselezionando una casella di controllo nelle proprietà del progetto in Visual Studio.

### <a name="disable-through-project-properties"></a>Disabilitare tramite le proprietà del progetto

Se si dispone di Visual Studio 2017 versione 15,7 o successiva, è possibile disabilitare facilmente i reindirizzamenti di binding generati automaticamente nelle pagine delle proprietà del progetto.

1. Fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e scegliere **Proprietà**.

2. Nella pagina dell' **applicazione** deselezionare l'opzione per la **generazione automatica dei reindirizzamenti di binding** .

3. Premere **CTRL** + **S** per salvare la modifica.

### <a name="disable-manually-in-the-project-file"></a>Disabilitare manualmente nel file di progetto

1. Aprire il file di progetto per la modifica utilizzando uno dei metodi seguenti:

   - In Visual Studio selezionare il progetto in **Esplora soluzioni**, quindi scegliere **Apri cartella in Esplora file** dal menu di scelta rapida. In Esplora file trovare il file di progetto (con estensione csproj o vbproj) e aprirlo nel blocco note.
   - In Visual Studio, in **Esplora soluzioni**, fare clic con il pulsante destro del mouse sul progetto e scegliere **Scarica progetto**. Fare di nuovo clic con il pulsante destro del mouse sul progetto scaricato, quindi scegliere **modifica [NomeProgetto. csproj]**.

2. Nel file di progetto trovare la voce di proprietà seguente:

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. Modificare `true` in `false`:

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a>Abilita manualmente i reindirizzamenti di binding automatici

È possibile abilitare reindirizzamenti di binding automatici nelle app esistenti destinate a versioni precedenti del .NET Framework o nei casi in cui non viene automaticamente richiesto di aggiungere un reindirizzamento. Se la destinazione è una versione più recente del Framework, ma non viene automaticamente richiesto di aggiungere un reindirizzamento, probabilmente si otterrà un output di compilazione che suggerisce di modificare il mapping degli assembly.

1. Aprire il file di progetto per la modifica utilizzando uno dei metodi seguenti:

   - In Visual Studio selezionare il progetto in **Esplora soluzioni**, quindi scegliere **Apri cartella in Esplora file** dal menu di scelta rapida. In Esplora file trovare il file di progetto (con estensione csproj o vbproj) e aprirlo nel blocco note.
   - In Visual Studio, in **Esplora soluzioni**, fare clic con il pulsante destro del mouse sul progetto e scegliere **Scarica progetto**. Fare di nuovo clic con il pulsante destro del mouse sul progetto scaricato, quindi scegliere **modifica [NomeProgetto. csproj]**.

2. Aggiungere l'elemento seguente al primo gruppo di proprietà di configurazione (sotto il \<PropertyGroup> tag):

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   Di seguito è riportato un esempio di file di progetto con l'elemento inserito:

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
     <PropertyGroup>
       <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
       <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
       <ProjectGuid>{123334}</ProjectGuid>
       ...
       <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
     </PropertyGroup>
     ...
   </Project>
   ```

3. Compilare l'app.

## <a name="enable-automatic-binding-redirects-in-web-apps"></a>Abilitare i reindirizzamenti di binding automatici nelle app Web

I reindirizzamenti di associazione automatici vengono implementati in modo diverso per le app Web. Poiché è necessario modificare il file di configurazione di origine (**web.config**) per le app Web, i reindirizzamenti di binding non vengono aggiunti automaticamente al file di configurazione. Visual Studio notifica, tuttavia, eventuali conflitti di associazione ed è possibile aggiungere reindirizzamenti di associazione per risolverli. Poiché viene sempre richiesto di aggiungere reindirizzamenti di binding, non è necessario disabilitare in modo esplicito questa funzionalità per un'app Web.

Per aggiungere reindirizzamenti di binding a un file di **web.config** :

1. In Visual Studio compilare l'app e cercare eventuali avvisi di compilazione.

   ![Avviso di compilazione per conflitti di riferimenti all'assembly](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")

2. In caso di conflitti di associazione a livello di assembly, viene visualizzato un avviso. Fare doppio clic sull'avviso oppure selezionare l'avviso e premere **invio**.

   Viene visualizzata una finestra di dialogo che consente di aggiungere automaticamente i reindirizzamenti di binding necessari al file di **web.config** di origine.

   ![Finestra di dialogo dell'autorizzazione reindirizzamento associazione](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")

## <a name="see-also"></a>Vedere anche

- [\<bindingRedirect>Elemento](./file-schema/runtime/bindingredirect-element.md)
- [Reindirizzamento delle versioni di assembly](redirect-assembly-versions.md)
