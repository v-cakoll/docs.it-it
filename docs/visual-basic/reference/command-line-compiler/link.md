---
title: -link
ms.date: 03/10/2018
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
ms.openlocfilehash: ecb7b0448b8ee9c1c1fc1eb9542b693d60a38ffd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335853"
---
# <a name="-link-visual-basic"></a>-link (Visual Basic)
Indica al compilatore di rendere disponibili al progetto in fase di compilazione le informazioni sui tipi COM presenti negli assembly specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-link:fileList  
```

Oppure  

```console
-l:fileList  
```  
  
## <a name="arguments"></a>argomenti  
  
|Termine|Definizione|  
|---|---|  
|`fileList`|Obbligatorio. Elenco di nomi di file di assembly delimitato da virgole. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.|  
  
## <a name="remarks"></a>Note  
 L'opzione `-link`consente di distribuire un'applicazione in cui sono incorporate informazioni sul tipo. L'applicazione può quindi usare i tipi in un assembly di runtime che implementano le informazioni sul tipo incorporate senza dovere far riferimento all'assembly di runtime. Se vengono pubblicate diverse versioni dell'assembly di runtime, l'applicazione che contiene le informazioni sul tipo incorporate può funzionare con le diverse versioni senza che sia necessaria la ricompilazione. Per un esempio, vedere [Procedura dettagliata: incorporamento dei tipi da assembly gestiti](../../../standard/assembly/embed-types-visual-studio.md).  
  
 L'opzione `-link` è particolarmente utile quando si usa l'interoperabilità COM. È possibile incorporare tipi COM in modo che per l'applicazione non sia più necessario un assembly di interoperabilità primario nel computer di destinazione. L'opzione `-link` indica al compilatore di incorporare le informazioni sul tipo COM dall'assembly di interoperabilità a cui si fa riferimento nel codice compilato risultante. Il tipo COM viene identificato dal valore CLSID (GUID). Di conseguenza, l'applicazione può essere eseguita in un computer di destinazione in cui sono stati installati gli stessi tipi COM con gli stessi valori CLSID. Le applicazioni che consentono di automatizzare Microsoft Office costituiscono un valido esempio. Poiché applicazioni come Office mantengono in genere lo stesso valore CLSID in versioni diverse, l'applicazione può usare i tipi COM a cui si fa riferimento purché .NET Framework 4 o versioni successive sia installato nel computer di destinazione e l'applicazione usi metodi, proprietà o eventi inclusi nei tipi COM a cui si fa riferimento.  
  
 L'opzione `-link` incorpora solo interfacce, strutture e delegati. L'incorporamento di classi COM non è supportato.  
  
> [!NOTE]
> Quando si crea un'istanza di un tipo COM incorporato nel codice, è necessario creare l'istanza usando l'interfaccia appropriata. Il tentativo di creare un'istanza di un tipo COM incorporato usando la coclasse genera un errore.  
  
 Per impostare l'opzione `-link` in Visual Studio, aggiungere un riferimento all'assembly e impostare la proprietà `Embed Interop Types` su **true**. Il valore predefinito della proprietà `Embed Interop Types` è **false**.  
  
 Se si collega a un assembly COM (assembly A) che fa riferimento a un altro assembly COM (assembly B), è necessario eseguire il collegamento anche all'assembly B se si verifica una delle condizioni seguenti:  
  
- Un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dall'assembly B.  
  
- Viene richiamato un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.  
  
 Use [-libpath](libpath.md) to specify the directory in which one or more of your assembly references is located.  
  
 Like the [-reference](reference.md) compiler option, the `-link` compiler option uses the Vbc.rsp response file, which references frequently used .NET Framework assemblies. Use the [-noconfig](noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.  
  
 La forma breve di `-link` è `-l`.  
  
## <a name="generics-and-embedded-types"></a>Generics e tipi incorporati  
 Nelle sezioni seguenti vengono descritte le limitazioni all'uso di tipi generici in applicazioni che incorporano tipi di interoperabilità.  
  
### <a name="generic-interfaces"></a>Interfacce generiche  
 Le interfacce generiche incorporate da un assembly di interoperabilità non possono essere usate, come illustrato nell'esempio riportato di seguito.  
  
 [!code-vb[VbLinkCompiler#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#1)]  
  
### <a name="types-that-have-generic-parameters"></a>Tipi con parametri generici  
 I tipi che hanno un parametro generico il cui tipo è incorporato da un assembly di interoperabilità non possono essere usati se tale tipo proviene da un assembly esterno. Tale restrizione non si applica tuttavia alle interfacce. Si consideri ad esempio l'interfaccia <xref:Microsoft.Office.Interop.Excel.Range> definita nell'assembly <xref:Microsoft.Office.Interop.Excel>. Se una libreria incorpora tipi di interoperabilità dall'assembly <xref:Microsoft.Office.Interop.Excel> ed espone un metodo che restituisce un tipo generico che ha un parametro il cui tipo è l'interfaccia <xref:Microsoft.Office.Interop.Excel.Range>, il metodo deve restituire un'interfaccia generica, come illustrato nell'esempio di codice seguente.  
  
 [!code-vb[VbLinkCompiler#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#2)]  
[!code-vb[VbLinkCompiler#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#3)]  
[!code-vb[VbLinkCompiler#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#4)]  
  
 Nell'esempio seguente, il codice client può chiamare il metodo che restituisce l'interfaccia generica <xref:System.Collections.IList> senza errori.  
  
 [!code-vb[VbLinkCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#5)]  
  
## <a name="example"></a>Esempio  
 The following command line compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.  
  
```console  
vbc -link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti](../../../standard/assembly/embed-types-visual-studio.md)
- [-reference (Visual Basic)](reference.md)
- [-noconfig](noconfig.md)
- [-libpath](libpath.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Introduzione all'interoperabilità COM](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
