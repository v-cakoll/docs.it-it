---
title: Selezionare la versione del linguaggio Visual Basic
description: Configurare il compilatore per eseguire la convalida della sintassi usando una specifica versione del compilatore.
ms.date: 05/24/2018
ms.openlocfilehash: 7628b5a7c27f5b26171d42e44a58598ef3d5d49f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194722"
---
# <a name="select-the-visual-basic-language-version"></a>Selezionare la versione del linguaggio Visual Basic

Il compilatore Visual Basic per impostazione predefinita la versione principale più recente del linguaggio che è stata rilasciata. È possibile scegliere di compilare tutti i progetti usando una nuova versione intermedia del linguaggio. La scelta di una versione più recente del linguaggio consente al progetto di usare le nuove funzionalità del linguaggio. In altri scenari può essere necessario verificare che un progetto viene compilato senza errori quando si usa una versione precedente del linguaggio.

Questa funzionalità separa l'installazione delle nuove versioni dell'SDK e degli strumenti nell'ambiente di sviluppo dalla decisione di incorporare nuove funzionalità del linguaggio in un progetto. È possibile installare l'SDK e gli strumenti più recenti nel computer di compilazione. Ogni progetto può essere configurato per usare una versione specifica del linguaggio in base alla relativa build.

Esistono tre modi per impostare la versione del linguaggio:

- Modificare manualmente il [ **vbproj** file](#edit-the-vbproj-file)
- Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects)
- Configurare il [ `-langversion` opzione del compilatore](#set-the-langversion-compiler-option)

## <a name="edit-the-vbproj-file"></a>Modificare il file vbproj

È possibile impostare la versione del linguaggio nel **vbproj** file. Aggiungere l'elemento seguente:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Il valore `latest` Usa la versione secondaria più recente del linguaggio Visual Basic. I valori validi sono:

|Valore|Significato|
|------------|-------------|
|default|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione principale più recente supportata.|
|9|Il compilatore accetta solo la sintassi inclusa in Visual Basic 9.0 o inferiore.|
|10|Il compilatore accetta solo la sintassi inclusa in Visual Basic 10.0 o inferiore.|
|11|Il compilatore accetta solo la sintassi inclusa in Visual Basic 11.0 o inferiore.|
|12|Il compilatore accetta solo la sintassi inclusa in Visual Basic 12.0 o inferiore.|
|14|Il compilatore accetta solo la sintassi inclusa in Visual Basic 14.0 o inferiore.|
|15|Il compilatore accetta solo la sintassi inclusa in Visual Basic 15.0 o inferiore.|
|15.3|Il compilatore accetta solo la sintassi inclusa in Visual Basic 15.3 o inferiore.|
|15.5|Il compilatore accetta solo la sintassi inclusa in Visual Basic 15.5 o inferiore.|
|latest|Il compilatore accetta tutte le sintassi di linguaggio valide.|

Le stringhe speciali `default` e `latest` si risolvono rispettivamente nelle versioni principale e secondaria più recenti del linguaggio installate nel computer di compilazione.

## <a name="configure-multiple-projects"></a>Configurare più progetti

È possibile creare un file **Directory.build.props** che contiene l'elemento `<LangVersion>` per configurare più directory. Questa operazione viene in genere eseguita nella directory della soluzione. Aggiungere quanto segue a un file **Directory.build.props** nella directory della soluzione:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>15.5</LangVersion>
 </PropertyGroup>
</Project>
```

A questo punto, le compilazioni in tutte le sottodirectory della directory contenente file userà la sintassi di Visual Basic versione 15.5. Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build.md).

## <a name="set-the-langversion-compiler-option"></a>Impostare l'opzione del compilatore langversion

È possibile usare l'opzione della riga di comando `-langversion`. Per altre informazioni, vedere l'articolo relativo all'opzione del compilatore [-langversion](../reference/command-line-compiler/langversion.md). È possibile visualizzare un elenco dei valori validi digitando `vbc -langversion:?` .
