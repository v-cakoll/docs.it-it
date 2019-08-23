---
title: 'Procedura: Creare criteri editore'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: bf5b55eb01a31106fcc7cb0d79212416ab0c898d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913052"
---
# <a name="how-to-create-a-publisher-policy"></a>Procedura: Creare criteri editore
I fornitori di assembly possono dichiarare che le applicazioni devono usare una versione più recente di un assembly includendo un file dei criteri editore con l'assembly aggiornato. Il file dei criteri editore specifica il reindirizzamento degli assembly e le impostazioni di base del codice e usa lo stesso formato di un file di configurazione dell'applicazione. Il file dei criteri editore viene compilato in un assembly e inserito nella Global Assembly Cache.  
  
 Per la creazione di un criterio editore sono necessari tre passaggi:  
  
1. Creazione di un file dei criteri editore.  
  
2. Creare un assembly dei criteri editore.  
  
3. Aggiungere l'assembly dei criteri editore al Global Assembly Cache.  
  
 Lo schema per i criteri editore è descritto in [Reindirizzamento delle versioni di assembly](redirect-assembly-versions.md). Nell'esempio seguente viene illustrato un file dei criteri dell'editore che reindirizza una versione `myAssembly` di a un'altra.  
  
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
 Usare [assembly linker (al. exe)](../tools/al-exe-assembly-linker.md) per creare l'assembly dei criteri editore.  
  
#### <a name="to-create-a-publisher-policy-assembly"></a>Per creare un assembly dei criteri editore  
  
1. Al prompt dei comandi digitare il comando seguente:  
  
     **al/link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/Platform:** *processorArchitecture*  
  
     In questo comando:  
  
    - L'argomento *publisherPolicyFile* è il nome del file dei criteri editore.  
  
    - L'argomento *publisherPolicyAssemblyFile* è il nome dell'assembly dei criteri editore risultante da questo comando. Il nome del file di assembly deve avere il formato seguente:  
  
         **policy.** *majorNumber* **.** *minorNumber* **.** *mainAssemblyName* **.dll**  
  
    - L'argomento *keyPairFile* è il nome del file che contiene la coppia di chiavi. È necessario firmare l'assembly e l'assembly dei criteri editore con la stessa coppia di chiavi.  
  
    - L'argomento *processorArchitecture* identifica la piattaforma di destinazione di un assembly specifico del processore.  
  
        > [!NOTE]
        >  La possibilità di definire come destinazione un'architettura del processore specifica è una novità della versione di .NET Framework 2,0.  
  
     Il comando che segue crea un assembly dei criteri `policy.1.0.myAssembly` editore chiamato da un file di `pub.config`criteri editore denominato, assegna un nome sicuro all'assembly usando `sgKey.snk` la coppia di chiavi nel file e specifica che l'assembly è destinato a x86 architettura del processore.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     L'assembly dei criteri dell'editore deve corrispondere all'architettura del processore dell'assembly a cui si applica. Pertanto, se l'assembly ha un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> <xref:System.Reflection.ProcessorArchitecture.MSIL>valore, l'assembly dei criteri dell'editore per tale assembly deve essere creato `/platform:anycpu`con. È necessario fornire un assembly dei criteri di pubblicazione separato per ogni assembly specifico del processore.  
  
     Una conseguenza di questa regola è che, per modificare l'architettura del processore per un assembly, è necessario modificare il componente principale o secondario del numero di versione, in modo che sia possibile fornire un nuovo assembly dei criteri editore con l'architettura del processore corretta. L'assembly dei criteri di pubblicazione precedente non può servire l'assembly quando l'assembly ha un'architettura del processore diversa.  
  
     Un'altra conseguenza è che non è possibile usare il linker versione 2,0 per creare un assembly dei criteri editore per un assembly compilato usando versioni precedenti del .NET Framework, perché specifica sempre l'architettura del processore.  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Aggiunta dell'assembly dei criteri editore alla Global assembly cache  
 Utilizzare lo [strumento Global Assembly Cache (Gacutil. exe)](../tools/gacutil-exe-gac-tool.md) per aggiungere l'assembly dei criteri editore al Global assembly cache.  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Per aggiungere l'assembly dei criteri editore al Global Assembly Cache  
  
1. Al prompt dei comandi digitare il comando seguente:  
  
     **gacutil/i** *publisherPolicyAssemblyFile*  
  
     Il comando seguente aggiunge `policy.1.0.myAssembly.dll` al Global assembly cache.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  Non è possibile aggiungere l'assembly dei criteri editore alla Global Assembly Cache a meno che il file dei criteri editore originale si trovi nella stessa directory dell'assembly.  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione con gli assembly](../app-domains/programming-with-assemblies.md)
- [Come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurazione di app tramite file di configurazione](index.md)
- [Schema delle impostazioni di runtime](./file-schema/runtime/index.md)
- [Schema dei file di configurazione](./file-schema/index.md)
- [Reindirizzamento delle versioni di assembly](redirect-assembly-versions.md)
