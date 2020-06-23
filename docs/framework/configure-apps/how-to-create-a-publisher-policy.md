---
title: 'Procedura: Creare criteri editore'
description: Informazioni sul modo in cui i fornitori di assembly possono creare un file dei criteri editore con un assembly aggiornato in .NET, per stabilire che le applicazioni devono usare la versione più recente.
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 23e9d8144ec5742e0371d566b7af59dc9dd30c9b
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105408"
---
# <a name="how-to-create-a-publisher-policy"></a>Procedura: Creare criteri editore

I fornitori di assembly possono dichiarare che le applicazioni devono usare una versione più recente di un assembly includendo un file dei criteri editore con l'assembly aggiornato. Il file dei criteri editore specifica il reindirizzamento degli assembly e le impostazioni di base del codice e usa lo stesso formato di un file di configurazione dell'applicazione. Il file dei criteri editore viene compilato in un assembly e inserito nella Global Assembly Cache.

Per la creazione di un criterio editore sono necessari tre passaggi:

1. Creazione di un file dei criteri editore.

2. Creare un assembly dei criteri editore.

3. Aggiungere l'assembly dei criteri editore al Global Assembly Cache.

Lo schema per i criteri editore è descritto in [Reindirizzamento delle versioni di assembly](redirect-assembly-versions.md). Nell'esempio seguente viene illustrato un file dei criteri dell'editore che reindirizza una versione di `myAssembly` a un'altra.

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

Per informazioni su come specificare una base di codice, vedere [specifica della posizione di un assembly](specify-assembly-location.md).

## <a name="creating-the-publisher-policy-assembly"></a>Creazione dell'assembly dei criteri editore

Usare [assembly linker (Al.exe)](../tools/al-exe-assembly-linker.md) per creare l'assembly dei criteri editore.

#### <a name="to-create-a-publisher-policy-assembly"></a>Per creare un assembly dei criteri editore

Al prompt dei comandi digitare il comando seguente:

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

In questo comando:

- L' `publisherPolicyFile` argomento è il nome del file dei criteri editore.

- L' `publisherPolicyAssemblyFile` argomento è il nome dell'assembly dei criteri editore risultante da questo comando. Il nome del file di assembly deve avere il formato seguente:

  'policy.majorNumber.minorNumber.mainAssemblyName.dll'

- L' `keyPairFile` argomento è il nome del file che contiene la coppia di chiavi. È necessario firmare l'assembly e l'assembly dei criteri editore con la stessa coppia di chiavi.

- L' `processorArchitecture` argomento identifica la piattaforma di destinazione di un assembly specifico del processore.

  > [!NOTE]
  > La possibilità di definire come destinazione un'architettura di processore specifica è disponibile a partire da .NET Framework 2,0.

La possibilità di definire come destinazione un'architettura di processore specifica è disponibile a partire da .NET Framework 2,0. Il comando che segue crea un assembly dei criteri editore chiamato `policy.1.0.myAssembly` da un file di criteri editore denominato `pub.config` , assegna un nome sicuro all'assembly usando la coppia di chiavi nel `sgKey.snk` file e specifica che l'assembly è destinato all'architettura del processore x86.

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

L'assembly dei criteri dell'editore deve corrispondere all'architettura del processore dell'assembly a cui si applica. Pertanto, se l'assembly ha un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> valore <xref:System.Reflection.ProcessorArchitecture.MSIL> , l'assembly dei criteri dell'editore per tale assembly deve essere creato con `/platform:anycpu` . È necessario fornire un assembly dei criteri di pubblicazione separato per ogni assembly specifico del processore.

Una conseguenza di questa regola è che, per modificare l'architettura del processore per un assembly, è necessario modificare il componente principale o secondario del numero di versione, in modo che sia possibile fornire un nuovo assembly dei criteri editore con l'architettura del processore corretta. L'assembly dei criteri di pubblicazione precedente non può servire l'assembly quando l'assembly ha un'architettura del processore diversa.

Un'altra conseguenza è che non è possibile usare il linker versione 2,0 per creare un assembly dei criteri editore per un assembly compilato usando versioni precedenti del .NET Framework, perché specifica sempre l'architettura del processore.

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Aggiunta dell'assembly dei criteri editore alla Global assembly cache

Utilizzare lo [strumento Global Assembly Cache (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per aggiungere l'assembly dei criteri editore al Global assembly cache.

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Per aggiungere l'assembly dei criteri editore al Global Assembly Cache

Al prompt dei comandi digitare il comando seguente:

```console
gacutil /i publisherPolicyAssemblyFile
```

Il comando seguente aggiunge `policy.1.0.myAssembly.dll` al Global assembly cache.

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> Non è possibile aggiungere l'assembly dei criteri editore alla Global Assembly Cache a meno che il file dei criteri editore originale specificato nell' `/link` argomento non si trovi nella stessa directory dell'assembly.

## <a name="see-also"></a>Vedere anche

- [Programmazione con gli assembly](../../standard/assembly/index.md)
- [Modalità di individuazione degli assembly da parte del runtime](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurazione delle app tramite file di configurazione](index.md)
- [Schema delle impostazioni di runtime](./file-schema/runtime/index.md)
- [Schema del file di configurazione](./file-schema/index.md)
- [Reindirizzamento delle versioni di assembly](redirect-assembly-versions.md)
