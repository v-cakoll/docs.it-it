---
title: -link (opzioni del compilatore C#)
ms.date: 07/20/2015
helpviewer_keywords:
- /l compiler option [C#]
- /link compiler option [C#]
- -l compiler option [C#]
- EmbedInteropTypes
- l compiler option [C#]
- embed interop types [COM Interop]
- -link compiler option [C#]
- link compiler option [C#]
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
ms.openlocfilehash: d5684298bbd736cae2d9c13381431036806aab17
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144461"
---
# <a name="-link-c-compiler-options"></a>-link (opzioni del compilatore C#)
Indica al compilatore di rendere disponibili al progetto in fase di compilazione le informazioni sui tipi COM presenti negli assembly specificati.

## <a name="syntax"></a>Sintassi

```console
-link:fileList
// -or-
-l:fileList
```

## <a name="arguments"></a>Argomenti
 `fileList`  
 Obbligatorio. Elenco di nomi di file di assembly delimitato da virgole. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.

## <a name="remarks"></a>Commenti
 L'opzione `-link`consente di distribuire un'applicazione in cui sono incorporate informazioni sul tipo. L'applicazione può quindi usare i tipi in un assembly di runtime che implementano le informazioni sul tipo incorporate senza dovere far riferimento all'assembly di runtime. Se vengono pubblicate diverse versioni dell'assembly di runtime, l'applicazione che contiene le informazioni sul tipo incorporate può funzionare con le diverse versioni senza che sia necessaria la ricompilazione. Per un esempio, vedere [Procedura dettagliata: incorporamento dei tipi da assembly gestiti](../../../standard/assembly/embed-types-visual-studio.md).

 L'opzione `-link` è particolarmente utile quando si usa l'interoperabilità COM. È possibile incorporare tipi COM in modo che per l'applicazione non sia più necessario un assembly di interoperabilità primario nel computer di destinazione. L'opzione `-link` indica al compilatore di incorporare le informazioni sul tipo COM dall'assembly di interoperabilità a cui si fa riferimento nel codice compilato risultante. Il tipo COM viene identificato dal valore CLSID (GUID). Di conseguenza, l'applicazione può essere eseguita in un computer di destinazione in cui sono stati installati gli stessi tipi COM con gli stessi valori CLSID. Le applicazioni che consentono di automatizzare Microsoft Office costituiscono un valido esempio. Poiché applicazioni come Office mantengono in genere lo stesso valore CLSID in versioni diverse, l'applicazione può usare i tipi COM a cui si fa riferimento purché .NET Framework 4 o versioni successive sia installato nel computer di destinazione e l'applicazione usi metodi, proprietà o eventi inclusi nei tipi COM a cui si fa riferimento.

 L'opzione `-link` incorpora solo interfacce, strutture e delegati. L'incorporamento di classi COM non è supportato.

> [!NOTE]
> Quando si crea un'istanza di un tipo COM incorporato nel codice, è necessario creare l'istanza usando l'interfaccia appropriata. Il tentativo di creare un'istanza di un tipo COM incorporato usando la coclasse genera un errore.

 Per impostare l'opzione `-link` in Visual Studio, aggiungere un riferimento all'assembly e impostare la proprietà `Embed Interop Types` su **true**. Il valore predefinito della proprietà `Embed Interop Types` è **false**.

 Se si collega a un assembly COM (assembly A) che fa riferimento a un altro assembly COM (assembly B), è necessario eseguire il collegamento anche all'assembly B se si verifica una delle condizioni seguenti:

- Un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dall'assembly B.

- Viene richiamato un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.

 Come l'opzione del compilatore [-reference](./reference-compiler-option.md), l'opzione del compilatore `-link` usa il file di risposta csc.rsp, che fa riferimento agli assembly .NET Framework di uso più frequente. Usare l'opzione del compilatore [-noconfig](./noconfig-compiler-option.md) se non si vuole che il compilatore usi il file csc.rsp.

 La forma breve di `-link` è `-l`.

## <a name="generics-and-embedded-types"></a>Generics e tipi incorporati
 Nelle sezioni seguenti vengono descritte le limitazioni all'uso di tipi generici in applicazioni che incorporano tipi di interoperabilità.

### <a name="generic-interfaces"></a>Interfacce generiche
 Le interfacce generiche incorporate da un assembly di interoperabilità non possono essere usate, come illustrato nell'esempio seguente.

 [!code-csharp[VbLinkCompilerCS#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#1)]

### <a name="types-that-have-generic-parameters"></a>Tipi con parametri generici
 I tipi che hanno un parametro generico il cui tipo è incorporato da un assembly di interoperabilità non possono essere usati se tale tipo proviene da un assembly esterno. Tale restrizione non si applica tuttavia alle interfacce. Si consideri ad esempio l'interfaccia <xref:Microsoft.Office.Interop.Excel.Range> definita nell'assembly <xref:Microsoft.Office.Interop.Excel>. Se una libreria incorpora tipi di interoperabilità dall'assembly <xref:Microsoft.Office.Interop.Excel> ed espone un metodo che restituisce un tipo generico che ha un parametro il cui tipo è l'interfaccia <xref:Microsoft.Office.Interop.Excel.Range>, il metodo deve restituire un'interfaccia generica, come illustrato nell'esempio di codice seguente.

[!code-csharp[VbLinkCompilerCS#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs)]

 Nell'esempio seguente, il codice client può chiamare il metodo che restituisce l'interfaccia generica <xref:System.Collections.IList> senza errori.

 [!code-csharp[VbLinkCompilerCS#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#5)]

## <a name="example"></a>Esempio
 Nel codice riportato di seguito viene compilato il file di origine `OfficeApp.cs` e viene fatto riferimento agli assembly di `COMData1.dll` e `COMData2.dll` per generare `OfficeApp.exe`.

```csharp
csc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.cs
```

## <a name="see-also"></a>Vedi anche

- [Opzioni del compilatore C#](./index.md)
- [Procedura dettagliata: incorporamento dei tipi da assembly gestiti](../../../standard/assembly/embed-types-visual-studio.md)
- [-Reference (opzioni del compilatore C#)](./reference-compiler-option.md)
- [-noconfig (opzioni del compilatore C#)](./noconfig-compiler-option.md)
- [Compilazione dalla riga di comando con csc.exe](./command-line-building-with-csc-exe.md)
- [Cenni preliminari sull'interoperabilità](../../programming-guide/interop/interoperability-overview.md)
