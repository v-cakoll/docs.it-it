---
title: Firma ritardata di un assembly
ms.date: 08/19/2019
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 113df1ad3fc3ac1e27ebfef572494c1f15a3dbb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73733171"
---
# <a name="delay-sign-an-assembly"></a>Firma ritardata di un assembly

Un'organizzazione può avere una coppia di chiavi strettamente sorvegliata a cui gli sviluppatori non possono accedere quotidianamente. La chiave pubblica è spesso disponibile, ma l'accesso alla chiave privata è consentito solo ad alcune persone. Quando si sviluppano assembly con nome sicuro, in ogni assembly che fa riferimento all'assembly con nome sicuro di destinazione è contenuto un token della chiave pubblica usata per assegnare un nome sicuro all'assembly di destinazione. È quindi necessario che la chiave pubblica risulti disponibile durante il processo di sviluppo.

È possibile utilizzare la firma ritardata o parziale in fase di compilazione per riservare spazio nel file eseguibile portabile (PE) per la firma con nome sicuro, ma rinviare la firma effettiva fino a una fase successiva, in genere appena prima della spedizione dell'assembly.

Per ritardare la firma di un assieme:

1. Ottenere la parte di chiave pubblica della coppia di chiavi dall'organizzazione che eseguirà la firma finale. In genere questa chiave è sotto forma di un file *con estensione snk,* che può essere creato utilizzando [lo strumento nome sicuro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) fornito da Windows SDK.

2. Apporre annotazioni al codice sorgente per l'assembly usando due attributi personalizzati da <xref:System.Reflection>:

   - <xref:System.Reflection.AssemblyKeyFileAttribute>, che consente di passare il nome del file contenente la chiave pubblica come parametro al costruttore.

   - <xref:System.Reflection.AssemblyDelaySignAttribute>, che indica che la firma ritardata viene utilizzata passando **true** come parametro al relativo costruttore.

   Ad esempio:

   ```cpp
   [assembly:AssemblyKeyFileAttribute("myKey.snk")];
   [assembly:AssemblyDelaySignAttribute(true)];
   ```

   ```csharp
   [assembly:AssemblyKeyFileAttribute("myKey.snk")]
   [assembly:AssemblyDelaySignAttribute(true)]
   ```

   ```vb
   <Assembly:AssemblyKeyFileAttribute("myKey.snk")>
   <Assembly:AssemblyDelaySignAttribute(True)>
   ```

3. Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e riserva nel file PE lo spazio necessario per la firma completa con nome sicuro. La chiave pubblica reale deve essere memorizzata in fase di compilazione dell'assembly, in modo che gli altri assembly contenenti riferimenti a questo assembly siano in grado di ottenere la chiave da memorizzare nei relativi riferimenti di assembly.

4. Poiché l'assembly non dispone di una firma con nome sicuro valida, è necessario disattivare la verifica della firma di tale assembly. A tale scopo, usare l'opzione **-Vr** dello strumento Nome sicuro.

     Nell'esempio riportato di seguito viene disattivata la verifica per un assembly denominato *myAssembly.dll*.

   ```console
   sn –Vr myAssembly.dll
   ```

   Per disattivare la verifica delle piattaforme in cui non è possibile eseguire lo strumento Nome sicuro, come microprocessori avanzati del computer RISC (ARM), usare l'opzione **-Vk** per creare un file del Registro di sistema. Importare il file del Registro di sistema nel Registro di sistema del computer in cui si vuole disattivare la verifica. L'esempio seguente consente di creare un file del Registro di sistema per `myAssembly.dll`.

   ```console
   sn –Vk myRegFile.reg myAssembly.dll
   ```

   Con l'opzione **–Vr** o **–Vk,** è possibile includere facoltativamente un file *con estensione snk* per la firma della chiave di test.

   > [!WARNING]
   > Non usare i nomi sicuri per la sicurezza, poiché forniscono solo un'identità univoca.

   > [!NOTE]
   > Se si usa il ritardo della firma durante lo sviluppo con Visual Studio in un computer a 64 bit e si compila un assembly per **Qualsiasi CPU**, potrebbe essere necessario applicare due volte l'opzione **-Vr**. (In Visual Studio, **qualsiasi CPU** è un valore della proprietà di compilazione destinazione della **piattaforma;** quando si esegue la compilazione dalla riga di comando, è l'impostazione predefinita.) Per eseguire l'applicazione dalla riga di comando o da Esplora file, utilizzare la versione a 64 bit di [Sn.exe (strumento Nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md) per applicare l'opzione **-Vr** all'assembly. Per caricare l'assembly in Visual Studio in fase di progettazione, ad esempio se l'assembly contiene componenti usati da altri assembly nell'applicazione, usare la versione a 32 bit dello strumento Nome sicuro. Questo perché il compilatore JIT compila l'assembly nel codice nativo a 64 bit quando l'assembly viene eseguito dalla riga di comando e nel codice nativo a 32 bit quando l'assembly viene caricato nell'ambiente di progettazione.

5. Successivamente, di solito prima della consegna, sottoporre l'assembly all'autorità di firma dell'organizzazione per la firma con nome sicuro effettiva tramite l'opzione **-R** dello strumento Nome sicuro.

   Nell'esempio riportato di seguito viene firmato un assembly denominato *myAssembly.dll* con un nome sicuro utilizzando la coppia di chiavi *sgKey.snk.*

   ```console
   sn -R myAssembly.dll sgKey.snk
   ```

## <a name="see-also"></a>Vedere anche

- [Creare assembly](create.md)
- [Procedura: Creare una coppia di chiavi pubblica/privata](create-public-private-key-pair.md)
- [Sn.exe (strumento Nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md)
