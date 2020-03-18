---
title: 'Procedura: Creare una coppia di chiavi pubblica/privata'
ms.date: 08/20/2019
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 8a9845e3cd18ff86ec04216ad0e9c5606186b113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73122524"
---
# <a name="how-to-create-a-public-private-key-pair"></a>Procedura: Creare una coppia di chiavi pubblica/privata

Per firmare un assembly con un nome sicuro, è necessario disporre di una coppia di chiavi pubblica/privata. Questa coppia di chiavi crittografiche, pubblica e privata, viene usata durante la compilazione per creare un assembly con nome sicuro. È possibile creare una coppia di chiavi usando lo [strumento Nome sicuro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md). I file di coppia di chiavi hanno in genere un'estensione *.snk.*

> [!NOTE]
> In Visual Studio, le pagine delle proprietà del progetto di Visual Basic e di Visual Basic includono una scheda **Firma** che consente di selezionare i file di chiave esistenti o di generare nuovi file di chiave senza *utilizzare Sn.exe*. In Visual C++ è possibile specificare il percorso di un file di chiave esistente nella pagina delle proprietà **Avanzate** nella sezione **Linker** della sezione **Proprietà di configurazione** della finestra **Pagine delle proprietà**. L'utilizzo <xref:System.Reflection.AssemblyKeyFileAttribute> dell'attributo per identificare le coppie di file di chiave è stato reso obsoleto a partire da Visual Studio 2005.

## <a name="create-a-key-pair"></a>Creare una coppia di chiaviCreate a key pair

Per creare una coppia di chiavi, al prompt dei comandi digitare il comando seguente:

**sn –k** \<*nome file*>

In questo comando *nome file* corrisponde al nome del file di output contenente la coppia di chiavi.

Nell'esempio riportato di seguito viene creata una coppia di chiavi denominata *sgKey.snk*.

```cmd
sn -k sgKey.snk
```

Se si desidera ritardare la firma di un assembly e si controlla l'intera coppia di chiavi (situazione improbabile al di fuori degli scenari di testing), è possibile usare i comandi seguenti per generare una coppia di chiavi e quindi estrarre da tale coppia la chiave pubblica, che viene salvata in un file distinto. Creare innanzitutto la coppia di chiavi:

```cmd
sn -k keypair.snk
```

Estrarre quindi la chiave pubblica dalla coppia di chiavi e copiarla in un file distinto:

```cmd
sn -p keypair.snk public.snk
```

Dopo avere creato la coppia di chiavi, è necessario salvare il file in una posizione accessibile agli strumenti di firma con nome sicuro.

Quando firma un assembly con un nome sicuro, [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) cerca il file della chiave relativo alla directory corrente e alla directory di output. Se si utilizzano i compilatori della riga di comando, è sufficiente copiare la chiave nella directory corrente contenente i moduli di codice.

Se si usa una versione precedente di Visual Studio in cui non è disponibile una scheda **Firma** nelle proprietà del progetto, il percorso del file di chiave consigliato è la directory del progetto con l'attributo di file specificato come segue:

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

## <a name="see-also"></a>Vedere anche

- [Creare e usare gli assembly con nome sicuro](create-use-strong-named.md)
