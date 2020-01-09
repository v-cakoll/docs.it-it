---
title: Compilatore XSLT (xsltc.exe)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 672a5ac8-8305-4d28-ba10-11089c2c0924
ms.openlocfilehash: 83d880da65c2fc0730819f0a51c4e8b29deb4c8f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709725"
---
# <a name="xslt-compiler-xsltcexe"></a>Compilatore XSLT (xsltc.exe)
Il compilatore XSLT (xsltc.exe) consente di compilare fogli di stile XSLT e di generare un assembly. Il foglio di stile compilato può quindi essere passato direttamente nel metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>. Non è possibile generare assembly firmati con xsltc.exe.  
  
 Lo strumento xsltc.exe è incluso in Visual Studio. Per altre informazioni, vedere [Download di Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).  
  
## <a name="syntax"></a>Sintassi  
  
```console  
xsltc [options] [/class:<name>] <sourceFile> [[/class:<name>] <sourceFile>...]  
```  
  
## <a name="argument"></a>Argomento  
  
|Argomento|Descrizione|  
|--------------|-----------------|  
|`sourceFile`|Consente di specificare il nome del foglio di stile. Il foglio di stile deve essere un file locale o deve essere disponibile nella Intranet.|  
  
## <a name="options"></a>Options  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|`/c[lass]:` `name`|Consente di specificare il nome della classe del foglio di stile successivo. Il nome della classe può essere completo.<br /><br /> Per impostazione predefinita, il nome della classe corrisponde al nome del foglio di stile. Ad esempio, se viene compilato il foglio di stile customers.xsl, il nome predefinito della classe sarà customers.|  
|`/debug[`+&#124;-`]`|Consente di specificare se generare le informazioni per il debug.<br /><br /> Se si specifica `+` o `/debug`, il compilatore genererà le informazioni per il debug e le inserirà in un file del database di programma con estensione PDB. Il nome del file PDB generato è `assemblyName`.pdb.<br /><br /> Se si specifica l'argomento `-`, che è attivo quando `/debug` non è specificato, non verranno create informazioni per il debug. Verrà generato un assembly finale. **Nota:** la compilazione in modalità di debug può influire significativamente sulle prestazioni di XSLT.|  
|`/help`|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|`/nologo`|Consente di disattivare la visualizzazione del messaggio di copyright del compilatore.|  
|`/platform:` `string`|Consente di specificare le piattaforme in cui è possibile eseguire l'assembly. Di seguito sono illustrati i valori di piattaforma validi:<br /><br /> `x86`: consente di compilare l'assembly in modo che sia possibile eseguirlo con la versione x86 compatibile di Common Language Runtime a 32 bit.<br /><br /> `x64`: consente di compilare l'assembly in modo che sia possibile eseguirlo con Common Language Runtime a 64 bit su un computer che supporta il set di istruzioni AMD64 o EM64T.<br /><br /> Itanium compila l'assembly in modo che sia possibile eseguirlo con Common Language Runtime a 64 bit in un computer dotato di un processore Itanium.<br /><br /> `anycpu`: consente di compilare l'assembly in modo che sia possibile eseguirlo su qualsiasi piattaforma. Questo è il valore predefinito.|  
|`/out:` `assemblyName`|Specifica il nome dell'assembly che viene restituito come output. Per impostazione predefinita, il nome dell'assembly corrisponde al nome del foglio di stile principale o a quello del primo foglio di stile se esistono più fogli.<br /><br /> Se il foglio di stile contiene script, questi vengono salvati in un assembly distinto. I nomi degli assembly di script vengono generati dal nome dell'assembly principale. Ad esempio, se è stato specificato CustOrders.dll come nome dell'assembly, al primo assembly di script verrà assegnato il nome CustOrders_Script1.dll.|  
|`/settings:` `document+-, script+-, DTD+-,`|Consente di specificare se consentire l'uso di funzioni `document()`, script XSLT, o DTD (Document Type Definition) nel foglio di stile.<br /><br /> Per impostazione predefinita, il supporto per DTD, per la funzione `document()` e gli script è disabilitato.|  
|`@` `file`|Consente di specificare un file che contiene le opzioni del compilatore.|  
|`?`|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="remarks"></a>Note  
 Le soluzioni XSLT possono essere costituite da più moduli del foglio di stile. Lo strumento xsltc.exe genera assembly dai fogli di stile. Gli assembly possono quindi essere passati direttamente nel metodo <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>. Tale comportamento può contribuire a ridurre i costi correlati alle prestazioni in alcuni scenari di distribuzione di XSLT.  
  
> [!NOTE]
> È inoltre necessario includere anche l'assembly compilato come riferimento nell'applicazione.  
  
 Lo strumento xsltc.exe non convalida i nomi di classe (`/class:`*name*) o di assembly (`/out:`*assemblyName*). Se i nomi non sono validi, CLR genera errori.  
  
## <a name="examples"></a>Esempi  
 Il comando seguente consente di compilare il foglio di stile e di creare un assembly denominato booksort.dll.  
  
```console  
xsltc booksort.xsl  
```  
  
 Il comando seguente consente di compilare il foglio di stile e di creare un assembly e un file PDB denominati rispettivamente booksort.dll e booksort.pdb.  
  
```console  
xsltc booksort.xsl /debug  
```  
  
 Il comando seguente consente di compilare un foglio di stile che contiene l'elemento msxsl:script e di creare due assembly denominati calc.dll e calc_Script1.dll.  
  
```console  
xsltc /settings:script+ calc.xsl  
```  
  
 Il comando seguente consente di abilitare il supporto per gli script e per l'elaborazione DTD, nonché di creare due assembly denominati myTest.dll e myTest_Script1.dll.  
  
```console  
xsltc /settings:DTD+,script+ /out:myTest calc.xsl  
```  
  
 Il comando seguente consente di compilare due moduli di fogli di stile e di creare un unico assembly denominato booksort.dll.  
  
```console  
xsltc booksort.xsl output.xsl  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Xsl.XslCompiledTransform>
- [Procedura: Eseguire una trasformazione XSLT con un assembly](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md)
- [Trasformazioni XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
