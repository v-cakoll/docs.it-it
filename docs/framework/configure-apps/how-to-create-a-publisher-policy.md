---
title: 'Procedura: creare criteri editore'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e7cac3c7e6c588a82e9dfff169ba7b7aa72c35f8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399635"
---
# <a name="how-to-create-a-publisher-policy"></a>Procedura: creare criteri editore
I fornitori di assembly possono indicare che le applicazioni devono utilizzare una versione più recente di un assembly includendo un file dei criteri editore con l'assembly aggiornato. File dei criteri editore specifica il reindirizzamento di assembly e le impostazioni della codebase e Usa lo stesso formato di un file di configurazione dell'applicazione. File dei criteri editore viene compilato in un assembly e inserito nella global assembly cache.  
  
 Esistono tre passaggi coinvolti nella creazione di un criterio server di pubblicazione:  
  
1.  Creare un file dei criteri editore.  
  
2.  Creare un assembly dei criteri editore.  
  
3.  Aggiungere l'assembly dei criteri editore nella global assembly cache.  
  
 Lo schema dei criteri dell'editore è descritto nella [reindirizzamento delle versioni degli Assembly](../../../docs/framework/configure-apps/redirect-assembly-versions.md). L'esempio seguente illustra un server di pubblicazione file dei criteri che reindirizza una versione `myAssembly` a altro.  
  
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
  
 Per informazioni su come specificare una base di codice, vedere [che specifica la posizione dell'Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).  
  
## <a name="creating-the-publisher-policy-assembly"></a>Creazione di Assembly dei criteri editore  
 Usare la [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) per creare l'assembly del criterio server di pubblicazione.  
  
#### <a name="to-create-a-publisher-policy-assembly"></a>Per creare un assembly dei criteri editore  
  
1.  Digitare il comando seguente al prompt dei comandi:  
  
     **al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:**  *keyPairFile* **/platform:** *processorArchitecture*  
  
     In questo comando:  
  
    -   Il *publisherPolicyFile* argomento è il nome del file dei criteri editore.  
  
    -   Il *publisherPolicyAssemblyFile* argomento è il nome dell'assembly dei criteri editore risultante da questo comando. Nome file dell'assembly deve seguire il formato:  
  
         **policy.** *majorNumber* **.** *minorNumber* **.** *mainAssemblyName* **. dll**  
  
    -   Il *keyPairFile* argomento è il nome del file contenente la coppia di chiavi. È necessario firmare l'assembly e assembly dei criteri editore con la stessa coppia di chiavi.  
  
    -   Il *processorArchitecture* argomento identifica la piattaforma di destinazione da un assembly specifico del processore.  
  
        > [!NOTE]
        >  La possibilità di un'architettura di processore specifica di destinazione è le novità di .NET Framework versione 2.0.  
  
     Il comando seguente crea un assembly dei criteri editore chiamato `policy.1.0.myAssembly` chiamato da un file dei criteri editore `pub.config`, assegna un nome sicuro all'assembly usando la coppia di chiavi nel `sgKey.snk` file e specifica che l'assembly abbia come destinazione x86 architettura del processore.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     L'assembly dei criteri editore deve corrispondere all'architettura di processore dell'assembly che si applica a. Di conseguenza, se l'assembly ha un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> valore del <xref:System.Reflection.ProcessorArchitecture.MSIL>, l'assembly dei criteri editore per tale assembly deve essere creato con `/platform:anycpu`. È necessario fornire un oggetto separato assembly dei criteri editore per ogni assembly specifico del processore.  
  
     Una conseguenza di questa regola è che, per modificare l'architettura del processore per un assembly, è necessario modificare il componente principale o secondario del numero di versione, in modo che è possibile fornire un nuovo assembly dei criteri editore con l'architettura del processore corretta. Il vecchio assembly dei criteri editore non è in grado di soddisfare l'assembly dopo che l'assembly ha un'architettura di processore differente.  
  
     Un altro motivo, il linker versione 2.0 non può essere utilizzato per creare un assembly dei criteri editore per un assembly compilato con le versioni precedenti di .NET Framework, poiché viene specificata l'architettura del processore.  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Aggiunta di Assembly dei criteri editore per Global Assembly Cache  
 Usare la [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) per aggiungere l'assembly dei criteri editore nella global assembly cache.  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Per aggiungere l'assembly dei criteri editore nella global assembly cache  
  
1.  Digitare il comando seguente al prompt dei comandi:  
  
     **gacutil /i***publisherPolicyAssemblyFile*  
  
     Il seguente comando aggiunge `policy.1.0.myAssembly.dll` alla global assembly cache.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  Impossibile aggiungere l'assembly dei criteri editore nella global assembly cache, a meno che il file dei criteri editore originale si trova nella stessa directory dell'assembly.  
  
## <a name="see-also"></a>Vedere anche  
 [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Configurazione di applicazioni](../../../docs/framework/configure-apps/index.md)  
 [Configurazione delle app .NET Framework](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [Schema delle impostazioni di runtime](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../docs/framework/configure-apps/file-schema/index.md)  
 [Reindirizzamento delle versioni di assembly](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
