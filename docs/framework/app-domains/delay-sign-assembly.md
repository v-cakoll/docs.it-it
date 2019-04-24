---
title: Ritardo della firma di un assembly
ms.date: 07/31/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc955ca892a8a0e5d15710b76a6a1c798ad4ecf5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334055"
---
# <a name="delay-signing-an-assembly"></a>Ritardo della firma di un assembly
È possibile che in un'organizzazione venga usata una coppia di chiavi sottoposta a una rigorosa sicurezza e quindi non accessibile giornalmente agli sviluppatori. La chiave pubblica è spesso disponibile, ma l'accesso alla chiave privata è consentito solo ad alcune persone. Quando si sviluppano assembly con nome sicuro, in ogni assembly che fa riferimento all'assembly con nome sicuro di destinazione è contenuto un token della chiave pubblica usata per assegnare un nome sicuro all'assembly di destinazione. È quindi necessario che la chiave pubblica risulti disponibile durante il processo di sviluppo.  
  
 È possibile usare il ritardo della firma o la firma parziale in fase di compilazione per riservare nel file eseguibile trasportabile (PE, Portable Executable) lo spazio per la firma con nome sicuro, posticipando la firma effettiva a una fase successiva, solitamente prima della consegna dell'assembly.  
  
 I passaggi seguenti illustrano il processo che consente di ritardare la firma di un assembly:  
  
1. Ottenere la parte pubblica della coppia di chiavi dall'organizzazione da cui verrà effettivamente apposta la firma. Tale chiave si presenta solitamente sotto forma di file con estensione snk. È possibile creare questo file tramite lo [strumento Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) disponibile in [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].  
  
2. Apporre annotazioni al codice sorgente per l'assembly usando due attributi personalizzati da <xref:System.Reflection>:  
  
    -   <xref:System.Reflection.AssemblyKeyFileAttribute>, che consente di passare il nome del file contenente la chiave pubblica come parametro al costruttore.  
  
    -   <xref:System.Reflection.AssemblyDelaySignAttribute>, che indica che si sta usando il ritardo della firma passando **true** come parametro al costruttore. Ad esempio:  
  
         [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)]
         [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)]
         [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
3. Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e riserva nel file PE lo spazio necessario per la firma completa con nome sicuro. La chiave pubblica reale deve essere memorizzata in fase di compilazione dell'assembly, in modo che gli altri assembly contenenti riferimenti a questo assembly siano in grado di ottenere la chiave da memorizzare nei relativi riferimenti di assembly.  
  
4. Poiché l'assembly non dispone di una firma con nome sicuro valida, è necessario disattivare la verifica della firma di tale assembly. A tale scopo, usare l'opzione **-Vr** dello strumento Nome sicuro.  
  
     L'esempio seguente consente di disattivare la verifica per un assembly denominato `myAssembly.dll`.  
  
    ```  
    sn –Vr myAssembly.dll  
    ```  
  
     Per disattivare la verifica delle piattaforme in cui non è possibile eseguire lo strumento Nome sicuro, come microprocessori avanzati del computer RISC (ARM), usare l'opzione **-Vk** per creare un file del Registro di sistema. Importare il file del Registro di sistema nel Registro di sistema del computer in cui si vuole disattivare la verifica. L'esempio seguente consente di creare un file del Registro di sistema per `myAssembly.dll`.  
  
    ```  
    sn –Vk myRegFile.reg myAssembly.dll  
    ```  
  
     Con l'opzione **-Vr** o **-Vk** è possibile includere un file con estensione snk per la firma con una chiave di test.  
  
    > [!WARNING]
    > Non usare i nomi sicuri per la sicurezza, poiché forniscono solo un'identità univoca.
  
    > [!NOTE]
    >  Se si usa il ritardo della firma durante lo sviluppo con Visual Studio in un computer a 64 bit e si compila un assembly per **Qualsiasi CPU**, potrebbe essere necessario applicare due volte l'opzione **-Vr**. In Visual Studio **Qualsiasi CPU** è un valore della proprietà di compilazione **Piattaforma di destinazione**. Quando si esegue la compilazione dalla riga di comando, è l'impostazione predefinita. Per eseguire l'applicazione dalla riga di comando o da Esplora risorse, usare la versione a 64 bit di [Sn.exe (strumento Nome sicuro)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) per applicare l'opzione **-Vr** all'assembly. Per caricare l'assembly in Visual Studio in fase di progettazione, ad esempio se l'assembly contiene componenti usati da altri assembly nell'applicazione, usare la versione a 32 bit dello strumento Nome sicuro. Questo perché il compilatore JIT compila l'assembly nel codice nativo a 64 bit quando l'assembly viene eseguito dalla riga di comando e nel codice nativo a 32 bit quando l'assembly viene caricato nell'ambiente di progettazione.  
  
5. Successivamente, di solito prima della consegna, sottoporre l'assembly all'autorità di firma dell'organizzazione per la firma con nome sicuro effettiva tramite l'opzione **-R** dello strumento Nome sicuro.  
  
     L'esempio seguente consente di firmare un assembly denominato `myAssembly.dll` con un nome sicuro usando la coppia di chiavi `sgKey.snk`.  
  
    ```  
    sn -R myAssembly.dll sgKey.snk  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Creazione degli assembly](../../../docs/framework/app-domains/create-assemblies.md)
- [Procedura: Creare una coppia di chiavi pubblica/privata](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [Sn.exe (strumento Nome sicuro)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)
- [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)
