---
title: 'Procedura: Creare una coppia di chiavi pubblica/privata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce346bfe0c20e94673009adb0134fbaab62cf551
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653918"
---
# <a name="how-to-create-a-public-private-key-pair"></a>Procedura: Creare una coppia di chiavi pubblica/privata

Per firmare un assembly con un nome sicuro, è necessario disporre di una coppia di chiavi pubblica/privata. Questa coppia di chiavi crittografiche, pubblica e privata, viene usata durante la compilazione per creare un assembly con nome sicuro. È possibile creare una coppia di chiavi usando lo [strumento Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md). Ai file delle coppie di chiavi è in genere associata l'estensione snk.

> [!NOTE]
> In Visual Studio le pagine delle proprietà del progetto C# e Visual Basic includono una scheda **Firma**, che consente di selezionare i file di chiave esistenti o di generarne di nuovi senza usare Sn.exe. In Visual C++ è possibile specificare il percorso di un file di chiave esistente nella pagina delle proprietà **Avanzate** nella sezione **Linker** della sezione **Proprietà di configurazione** della finestra **Pagine delle proprietà**. L'uso dell'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> per identificare le coppie di file di chiave è diventato obsoleto a partire da Visual Studio 2005.

## <a name="to-create-a-key-pair"></a>Per creare una coppia di chiavi

1.  Al prompt dei comandi digitare il seguente comando:

     **sn –k** \<*nome file*>

     In questo comando *nome file* corrisponde al nome del file di output contenente la coppia di chiavi.

 L'esempio seguente consente di creare una coppia di chiavi denominata `sgKey.snk`.

```
sn -k sgKey.snk
```

 Se si desidera ritardare la firma di un assembly e si controlla l'intera coppia di chiavi (situazione improbabile al di fuori degli scenari di testing), è possibile usare i comandi seguenti per generare una coppia di chiavi e quindi estrarre da tale coppia la chiave pubblica, che viene salvata in un file distinto. Creare innanzitutto la coppia di chiavi:

```
sn -k keypair.snk
```

 Estrarre quindi la chiave pubblica dalla coppia di chiavi e copiarla in un file distinto:

```
sn -p keypair.snk public.snk
```

 Dopo avere creato la coppia di chiavi, è necessario salvare il file in una posizione accessibile agli strumenti di firma con nome sicuro.

 Quando firma un assembly con un nome sicuro, [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) cerca il file della chiave relativo alla directory corrente e alla directory di output. Se si utilizzano i compilatori della riga di comando, è sufficiente copiare la chiave nella directory corrente contenente i moduli di codice.

 Se si usa una versione precedente di Visual Studio in cui non è disponibile una scheda **Firma** nelle proprietà del progetto, il percorso del file di chiave consigliato è la directory del progetto con l'attributo di file specificato come segue:

 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]

## <a name="see-also"></a>Vedere anche

- [Creazione e utilizzo degli assembly con nome sicuro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
