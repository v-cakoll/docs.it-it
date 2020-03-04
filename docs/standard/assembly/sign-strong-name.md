---
title: 'Procedura: firmare un assembly con un nome sicuro'
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 9998e69e8bf1505bcfc7a9103e9d89616dad9633
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160313"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a>Procedura: firmare un assembly con un nome sicuro

> [!NOTE]
> Sebbene .NET Core supporti assembly con nome sicuro e tutti gli assembly nella libreria .NET Core siano firmati, la maggior parte degli assembly di terze parti non necessita di nomi sicuri. Per altre informazioni, vedere [firma con nome sicuro](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) su GitHub.

Sono disponibili diversi modi per firmare un assembly con un nome sicuro:  
  
- Utilizzando la scheda di **Firma** nella finestra di dialogo **Proprietà** di un progetto in Visual Studio. Questo è il modo più semplice e più pratico per firmare un assembly con un nome sicuro.  
  
- Usando [assembly linker (al. exe)](../../framework/tools/al-exe-assembly-linker.md) per collegare un modulo di codice .NET Framework (un file con estensione *netmodule* ) con un file di chiave.  
  
- Utilizzando attributi dell'assembly per inserire le informazioni relative al nome sicuro nel codice. È possibile utilizzare l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> , a seconda della posizione del file di chiave da utilizzare.  
  
- Utilizzando le opzioni del compilatore.  
  
 Per firmare un assembly con un nome sicuro, è necessario disporre di una coppia di chiavi crittografiche. Per ulteriori informazioni sulla creazione di una coppia di chiavi, vedere [procedura: creare una coppia di chiavi pubblica/privata](create-public-private-key-pair.md).  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a>Creare e firmare un assembly con un nome sicuro usando Visual Studio  
  
1. In **Esplora soluzioni**aprire il menu di scelta rapida per il progetto, quindi scegliere **Proprietà**.  
  
2. Scegliere la scheda **Firma** .  
  
3. Selezionare la casella **Firma assembly** .  
  
4. Nella casella **Scegli un file chiave con nome sicuro** scegliere **Sfoglia**e quindi passare al file di chiave. Per creare un nuovo file di chiave, scegliere **nuovo** e immettere il nome nella finestra di dialogo **Crea chiave con nome sicuro** .  
  
> [!NOTE]
> Per [ritardare la firma di un assembly](delay-sign.md), scegliere un file di chiave pubblica.  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a>Creare e firmare un assembly con un nome sicuro usando assembly linker  
  
Nel [prompt dei comandi per gli sviluppatori per Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), immettere il comando seguente:  

**al** **/out:**\<*assemblyName*> *\<ModuleName >* **/keyfile:**\<*fileFileName*>  

Dove:  

- *AssemblyName* è il nome dell'assembly fortemente firmato (un file con estensione *dll* o *exe* ) che verrà generato da assembly linker.  
  
- *ModuleName* è il nome di un modulo di codice .NET Framework (un file con estensione *netmodule* ) che include uno o più tipi. È possibile creare un file con *estensione netmodule* compilando il codice con l'opzione C# `/target:module` in o Visual Basic.
  
- *fileFileName* è il nome del contenitore o del file che contiene la coppia di chiavi. Assembly linker interpreta un percorso relativo in relazione alla directory corrente.  

Nell'esempio seguente l'assembly MyAssembly *. dll* viene firmato con un nome sicuro utilizzando il file di chiave *sgKey. snk*.  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
Per ulteriori informazioni sull'utilizzo di questo strumento, vedere [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a>Firmare un assembly con un nome sicuro usando gli attributi  
  
1. Aggiungere l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> o <xref:System.Reflection.AssemblyKeyNameAttribute> al file del codice sorgente, specificando il nome del file o del contenitore contenente la coppia di chiavi da utilizzare per la firma dell'assembly con un nome sicuro.  

2. Compilare normalmente il file del codice sorgente.  

   > [!NOTE]
   > Nei compilatori C# e Visual Basic vengono pubblicati avvisi del compilatore (rispettivamente CS1699 e BC41008) quando viene rilevato l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> nel codice sorgente. È possibile ignorare gli avvisi.  

Nell'esempio seguente viene usato l'attributo <xref:System.Reflection.AssemblyKeyFileAttribute> con un file di chiave denominato Key *file. snk*, che si trova nella directory in cui viene compilato l'assembly.  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

È inoltre possibile ritardare la firma di un assembly durante la compilazione del file del codice sorgente. Per altre informazioni, vedere [ritardare la firma di un assembly](delay-sign.md).  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a>Firmare un assembly con un nome sicuro utilizzando il compilatore  

Compilare il file o i file del codice sorgente con l'opzione del compilatore `/keyfile` o `/delaysign` in C# e Visual Basic o con l'opzione del linker `/KEYFILE` o `/DELAYSIGN` in C++. Dopo il nome di opzione, aggiungere due punti e il nome del file di chiave. Se si utilizzano compilatori della riga di comando, è possibile copiare il file di chiave nella directory contenente i file del codice sorgente.  

Per informazioni sulla firma ritardata, vedere [ritardare la firma di un assembly](delay-sign.md).  

Nell'esempio seguente viene usato C# il compilatore e viene firmato l'assembly *UtilityLibrary. dll* con un nome sicuro usando il file di chiave *sgKey. snk*.  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a>Vedere anche

- [Creazione e utilizzo di assembly con nome sicuro](create-use-strong-named.md)
- [Procedura: Creare una coppia di chiavi pubblica/privata](create-public-private-key-pair.md)
- [Al.exe (Assembly Linker)](../../framework/tools/al-exe-assembly-linker.md)
- [Ritardare la firma di un assembly](delay-sign.md)
- [Gestire le firme di assembly e manifesti](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [Pagina Firma, Creazione progetti](/visualstudio/ide/reference/signing-page-project-designer)
