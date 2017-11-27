---
title: 'Procedura: configurare i componenti COM basati su .NET Framework per l''attivazione senza registrazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d373d6abc82e482a3b1df873295573f0e34eeda2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a>Procedura: configurare i componenti COM basati su .NET Framework per l'attivazione senza registrazione
L'attivazione senza registrazione per i componenti basati su .NET Framework risulta solo leggermente più complessa rispetto a quella per i componenti COM. La configurazione richiede due manifesti:  
  
-   Per identificare il componente gestito, le applicazioni COM devono disporre di un manifesto dell'applicazione di tipo Win32.  
  
-   I componenti basati su .NET Framework devono disporre di un manifesto del componente per le informazioni sull'attivazione necessarie in fase di esecuzione.  
  
 Questo argomento descrive come associare un manifesto dell'applicazione a un'applicazione, come associare un manifesto del componente a un componente e come incorporare un manifesto del componente in un assembly.  
  
### <a name="to-create-an-application-manifest"></a>Per creare un manifesto dell'applicazione  
  
1.  Usando un editor XML, creare o modificare il manifesto dell'applicazione di proprietà dell'applicazione COM che interagisce con uno o più componenti gestiti.  
  
2.  Inserire l'intestazione standard seguente all'inizio del file:  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     Per informazioni sugli elementi del manifesto e i relativi attributi, vedere [manifesti dell'applicazione](https://msdn.microsoft.com/library/windows/desktop/aa374191.aspx).  
  
3.  Identificare il proprietario del manifesto. Nell'esempio seguente il proprietario del file manifesto è `myComApp` versione 1.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="msil"   
      />  
    ```  
  
4.  Identificare gli assembly dipendenti. Nell'esempio seguente, `myComApp` dipende da `myManagedComp`.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="x86"   
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myManagedComp"   
                        version="6.0.0.0"   
                        processorArchitecture="X86"   
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5.  Salvare il file manifesto assegnando un nome a questo. Il nome di un manifesto dell'applicazione è costituito dal nome dell'eseguibile dell'assembly seguito dall'estensione manifest. Il nome file del manifesto dell'applicazione per myComApp.exe, ad esempio, è myComApp.exe.manifest.  
  
 Un manifesto dell'applicazione può essere installato nella stessa directory dell'applicazione COM. In alternativa, può essere aggiunto come risorsa al file EXE dell'applicazione. Per ulteriori informazioni, per ulteriori informazioni, vedere [sugli assembly Side-by-Side](https://msdn.microsoft.com/library/windows/desktop/ff951640.aspx).  
  
#### <a name="to-create-a-component-manifest"></a>Per creare un manifesto del componente  
  
1.  Tramite un editor XML, creare un manifesto del componente per descrivere l'assembly gestito.  
  
2.  Inserire l'intestazione standard seguente all'inizio del file:  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3.  Identificare il proprietario del file. L'elemento `<assemblyIdentity>` dell'elemento `<dependentAssembly>` nel file manifesto dell'applicazione deve corrispondere a quello contenuto nel manifesto del componente. Nell'esempio seguente il proprietario del file manifesto è `myManagedComp` versione 1.2.3.4.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4.  Identificare ogni classe nell'assembly. Usare l'elemento `<clrClass>` per identificare in modo univoco ogni classe nell'assembly gestito. L'elemento, che costituisce un sottoelemento di `<assembly>` dispone degli attributi descritti nella tabella seguente.  
  
    |Attributo|Descrizione|Obbligatorio|  
    |---------------|-----------------|--------------|  
    |`clsid`|Identificatore che specifica la classe da attivare.|Sì|  
    |`description`|Stringa contenente informazioni sul componente. Il valore predefinito è una stringa vuota.|No|  
    |`name`|Stringa che rappresenta la classe gestita.|Sì|  
    |`progid`|Identificatore da usare per l'attivazione con associazione tardiva.|No|  
    |`threadingModel`|Modello di threading COM. "Both" è il valore predefinito.|No|  
    |`runtimeVersion`|Specifica la versione di Common Language Runtime (CLR) da usare. Se questo attributo non viene specificato e CLR non è ancora stato caricato, il componente viene caricato con l'ultimo CLR installato prima della versione 4. Se si specifica v1.0.3705, v1.1.4322 o v2.0.50727, la versione esegue automaticamente il roll forward all'ultima versione di CLR installata prima della versione 4 (di solito v2.0.50727). Se è già stata caricata un'altra versione di CLR ed è possibile caricare la versione specificata side-by-side in-process, la versione specificata viene caricata; in caso contrario, viene usato il CLR caricato. Ciò potrebbe causare un errore di caricamento.|No|  
    |`tlbid`|Identificatore della libreria dei tipi che contiene le informazioni sui tipi per la classe.|No|  
  
     Tutti i tag di attributo effettuano la distinzione tra maiuscole e minuscole. È possibile ottenere i CLSID, i ProgID, i modelli di threading e la versione del runtime visualizzando la libreria dei tipi esportata per l'assembly con il visualizzatore oggetti OLE/COM (Oleview.exe).  
  
     Nel manifesto del componente seguente vengono identificate due classi, `testClass1` e `testClass2`.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4" />  
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5.  Salvare il file manifesto assegnando un nome a questo. Il nome di un manifesto del componente è costituito dal nome della libreria dell'assembly seguito dall'estensione manifest. La libreria myManagedComp.dll, ad esempio, corrisponde a myManagedComp.manifest.  
  
 È necessario incorporare il manifesto del componente come risorsa nell'assembly.  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a>Per incorporare un manifesto del componente in un assembly gestito  
  
1.  Creare uno script di risorse contenente l'istruzione seguente:  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     In questa istruzione `myManagedComp.manifest` rappresenta il nome del manifesto del componente da incorporare. Nell'esempio, il nome file dello script è `myresource.rc`.  
  
2.  Compilare lo script tramite il compilatore di risorse di Microsoft Windows (Rc.exe) Al prompt dei comandi digitare il seguente comando:  
  
     `rc myresource.rc`  
  
     RC.exe genera il file di risorse `myresource.res`.  
  
3.  Compilare di nuovo il file di origine dell'assembly e specificare il file di risorse usando l'opzione **/win32res**:  
  
    ```  
    /win32res:myresource.res  
    ```  
  
     Anche in questo caso, `myresource.res` rappresenta il nome del file di risorse contenente la risorsa incorporata.  
  
## <a name="see-also"></a>Vedere anche  
 [Interoperabilità COM senza registrazione](../../../docs/framework/interop/registration-free-com-interop.md)  
 [Requisiti per l'interoperabilità COM senza registrazione](http://msdn.microsoft.com/en-us/0c43bc57-eecf-4e6c-8114-490141cce4da)  
 [Configurazione di componenti COM per l'attivazione senza registrazione](http://msdn.microsoft.com/en-us/bfe9b02f-d964-4784-960e-a1f94692fbfe)  
 [Registration-Free Activation of .NET-Based Components: A Walkthrough](http://go.microsoft.com/fwlink/?LinkId=158812) (Procedura dettagliata per l'attivazione senza registrazione di componenti basati su .NET)
