---
title: Selezionare la versione del linguaggio C# - Guida a C#
description: Configurare il compilatore per eseguire la convalida della sintassi con una versione specifica del compilatore
ms.date: 02/28/2019
ms.openlocfilehash: feb3e51a107f9830071b55c7985f202edc842f4a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770880"
---
# <a name="select-the-c-language-version"></a>Selezionare la versione del linguaggio C#

Il C# compilatore determina la versione di un linguaggio predefinito basata su uno o più framework di destinazione del progetto. Quando il progetto ha come destinazione un framework in anteprima con una versione del linguaggio in anteprima corrispondente, la versione del linguaggio usata è la versione del linguaggio in anteprima. Quando il progetto non ha come destinazione un framework in anteprima, la versione del linguaggio usata è la versione secondaria più recente.

Durante il periodo di anteprima per .NET Core 3.0, ad esempio, i progetti che hanno come destinazione `netcoreapp3.0` o `netstandard2.1` (entrambi in anteprima) useranno il linguaggio C# 8.0 (in anteprima). I progetti che hanno come destinazione una versione rilasciata useranno C# 7.3 (la versione rilasciata più recente). Con questo comportamento i progetti che hanno come destinazione .NET Framework useranno la versione più recente (C# 7.3). 

Questa funzionalità separa l'installazione delle nuove versioni dell'SDK e degli strumenti nell'ambiente di sviluppo dalla decisione di incorporare nuove funzionalità del linguaggio in un progetto. È possibile installare l'SDK e gli strumenti più recenti nel computer di compilazione. Ogni progetto può essere configurato per usare una versione specifica del linguaggio in base alla relativa build. Con il comportamento predefinito le funzionalità del linguaggio che si basano su nuovi tipi o sul nuovo comportamento CLR sono abilitate solo quando i progetti hanno come destinazione tali framework.

È possibile eseguire l'override del comportamento predefinito specificando una versione del linguaggio. La versione del linguaggio può essere impostata in modi diversi:

- Usare un'[azione rapida di Visual Studio](#visual-studio-quick-action).
- Impostare la versione del linguaggio nell'[interfaccia utente di Visual Studio](#set-the-language-version-in-visual-studio).
- Modificare manualmente il [file **.csproj**](#edit-the-csproj-file).
- Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects).
- Configurare l'[opzione del compilatore `-langversion`](#set-the-langversion-compiler-option).

## <a name="visual-studio-quick-action"></a>Azione rapida di Visual Studio

Visual Studio consente di determinare la versione del linguaggio necessaria. Se si usa una funzionalità del linguaggio non disponibile per la versione correntemente configurata, Visual Studio visualizza una correzione potenziale per aggiornare la versione del linguaggio per il progetto.

## <a name="set-the-language-version-in-visual-studio"></a>Impostare la versione del linguaggio in Visual Studio

È possibile impostare la versione in Visual Studio. Fare clic con il pulsante destro del mouse sul nodo del progetto in Esplora soluzioni e scegliere **Proprietà**. Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**. Nell'elenco a discesa selezionare la versione. L'immagine seguente mostra l'impostazione più recente:

![Screenshot delle impostazioni di compilazione avanzate in cui è possibile specificare la versione del linguaggio](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> Se si usa l'IDE di Visual Studio per aggiornare i file csproj, l'IDE crea nodi separati per ogni configurazione della build. In genere si imposta lo stesso valore in tutte le configurazioni della build, ma è necessario impostarlo in modo esplicito per ogni configurazione della build o selezionare "Tutte le configurazioni" quando si modifica questa impostazione. Nel file csproj verrà visualizzato quanto segue:
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a>Modificare il file csproj

È possibile impostare la versione del linguaggio nel file con estensione **csproj**. Aggiungere un elemento simile al seguente:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Il valore `latest` usa la versione secondaria più recente del linguaggio C#. I valori validi sono:

|Value|Significato|
|------------|-------------|
|preview|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione di anteprima più recente.|
|latest|Il compilatore accetta la sintassi dalla versione rilasciata più recente del compilatore (inclusa la versione secondaria).|
|latestMajor|Il compilatore accetta la sintassi dalla versione principale più recente rilasciata del compilatore.|
|8.0|Il compilatore accetta solo la sintassi inclusa in C# 8.0 o versione precedente.|
|7.3|Il compilatore accetta solo la sintassi inclusa in C# 7.3 o versione precedente.|
|7.2|Il compilatore accetta solo la sintassi inclusa in C# 7.2 o versione precedente.|
|7.1|Il compilatore accetta solo la sintassi inclusa in C# 7.1 o versione precedente.|
|7|Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione precedente.|
|6|Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione precedente.|
|5|Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione precedente.|
|4|Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione precedente.|
|3|Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione precedente.|
|ISO-2|Il compilatore accetta solo la sintassi inclusa nella specifica ISO/IEC 23270:2006 C# (2.0) |
|ISO-1|Il compilatore accetta solo la sintassi inclusa nella specifica ISO/IEC 23270:2003 C# (1.0/1.2) |

## <a name="configure-multiple-projects"></a>Configurare più progetti

È possibile creare un file **Directory.build.props** che contiene l'elemento `<LangVersion>` per configurare più directory. Questa operazione viene in genere eseguita nella directory della soluzione. Aggiungere il codice seguente a un file **Directory.Build.props** nella directory della soluzione:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

A questo punto, le compilazioni in tutte le sottodirectory della directory contenente il file useranno la sintassi di C# versione 7.3. Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build).

## <a name="set-the-langversion-compiler-option"></a>Impostare l'opzione del compilatore langversion

È possibile usare l'opzione della riga di comando `-langversion`. Per altre informazioni, vedere l'articolo relativo all'opzione del compilatore [-langversion](../language-reference/compiler-options/langversion-compiler-option.md). È possibile visualizzare un elenco dei valori validi digitando `csc -langversion:?`.
