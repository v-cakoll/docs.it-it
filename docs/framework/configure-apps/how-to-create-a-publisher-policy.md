---
title: 'Procedura: creare criteri editore'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646051"
---
# <a name="how-to-create-a-publisher-policy"></a>Procedura: creare criteri editore

I fornitori di assembly possono indicare che le applicazioni devono utilizzare una versione più recente di un assembly includendo un file dei criteri editore con l'assembly aggiornato. Il file dei criteri editore specifica il reindirizzamento dell'assembly e le impostazioni della base di codice e utilizza lo stesso formato di un file di configurazione dell'applicazione. Il file dei criteri editore viene compilato in un assembly e inserito nella Global Assembly Cache.

La creazione di criteri per l'editore prevede tre passaggi:There are three steps involved in creating a publisher policy:

1. Creare un file dei criteri dell'editore.

2. Creare un assembly dei criteri editore.

3. Aggiungere l'assembly dei criteri editore alla Global Assembly Cache.

Lo schema per i criteri editore è descritto in [Reindirizzamento delle versioni degli assembly](redirect-assembly-versions.md). Nell'esempio seguente viene illustrato un file `myAssembly` dei criteri editore che reindirizza una versione di a un'altra.

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
       <dependentAssembly>
         <assemblyIdentity name="myAssembly"
                           publicKeyToken="32ab4ba45e0a69a1"
                           culture="en-us" />
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->
         <bindingRedirect oldVersion="1.0.0.0"
                          newVersion="2.0.0.0"/>
       </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

Per informazioni su come specificare una base di codice, vedere [Specifica del percorso di un assieme](specify-assembly-location.md).

## <a name="creating-the-publisher-policy-assembly"></a>Creazione dell'assembly dei criteri editore

Utilizzare [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) per creare l'assembly dei criteri editore.

#### <a name="to-create-a-publisher-policy-assembly"></a>Per creare un assembly dei criteri editoreTo create a publisher policy assembly

Al prompt dei comandi digitare il comando seguente:

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

In questo comando:

- L'argomento `publisherPolicyFile` è il nome del file dei criteri editore.

- L'argomento `publisherPolicyAssemblyFile` è il nome dell'assembly dei criteri editore risultante da questo comando. Il nome del file di assieme deve seguire il formato:

  'policy.majorNumber.minorNumber.mainAssemblyName.dll'

- L'argomento `keyPairFile` è il nome del file contenente la coppia di chiavi. È necessario firmare l'assembly e l'assembly dei criteri editore con la stessa coppia di chiavi.

- L'argomento `processorArchitecture` identifica la piattaforma di destinazione di un assembly specifico del processore.

  > [!NOTE]
  > La possibilità di impostare come destinazione un'architettura di processore specifica a partire da .NET Framework 2.0.The ability to target a specific processor architecture is available starting with .NET Framework 2.0.

La possibilità di impostare come destinazione un'architettura di processore specifica a partire da .NET Framework 2.0.The ability to target a specific processor architecture is available starting with .NET Framework 2.0. Il comando riportato di `policy.1.0.myAssembly` seguito consente di `pub.config`creare un assembly dei criteri editore chiamato `sgKey.snk` da un file dei criteri editore denominato , assegna un nome sicuro all'assembly utilizzando la coppia di chiavi nel file e specifica che l'assembly è destinato all'architettura del processore x86.

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

L'assembly dei criteri editore deve corrispondere all'architettura del processore dell'assembly a cui si applica. Pertanto, se l'assembly ha un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> valore pari a <xref:System.Reflection.ProcessorArchitecture.MSIL>, `/platform:anycpu`l'assembly dei criteri editore per tale assembly deve essere creato con . È necessario fornire un assembly dei criteri editore separato per ogni assembly specifico del processore.

Una conseguenza di questa regola è che per modificare l'architettura del processore per un assembly, è necessario modificare il componente principale o secondario del numero di versione, in modo che sia possibile fornire un nuovo assembly dei criteri editore con l'architettura del processore corretta. L'assembly dei criteri editore precedente non può eseguire il servizio dell'assembly quando l'assembly ha un'architettura di processore diversa.

Un'altra conseguenza è che il linker della versione 2.0 non può essere utilizzato per creare un assembly dei criteri editore per un assembly compilato utilizzando versioni precedenti di .NET Framework, poiché specifica sempre l'architettura del processore.

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Aggiunta dell'assembly dei criteri editore alla Global Assembly Cache

Utilizzare lo [strumento Global Assembly Cache (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per aggiungere l'assembly dei criteri editore alla Global Assembly Cache.

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Per aggiungere l'assembly dei criteri editore alla Global Assembly Cache

Al prompt dei comandi digitare il comando seguente:

```console
gacutil /i publisherPolicyAssemblyFile
```

Il comando `policy.1.0.myAssembly.dll` seguente aggiunge alla Global Assembly Cache.

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> L'assembly dei criteri editore non può essere aggiunto alla `/link` Global Assembly Cache a meno che il file dei criteri editore originale specificato nell'argomento non si trovi nella stessa directory dell'assembly.

## <a name="see-also"></a>Vedere anche

- [Programmazione con gli assembly](../../standard/assembly/index.md)
- [Come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurazione delle app tramite file di configurazione](index.md)
- [Schema delle impostazioni di runtime](./file-schema/runtime/index.md)
- [Schema del file di configurazione](./file-schema/index.md)
- [Reindirizzamento delle versioni di assembly](redirect-assembly-versions.md)
