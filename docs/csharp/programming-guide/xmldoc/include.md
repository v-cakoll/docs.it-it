---
title: <include> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: bf41019c775fed25afe4bdb9453a8e52f44856b5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287350"
---
# <a name="include-c-programming-guide"></a>\<include>(Guida per programmatori C#)

## <a name="syntax"></a>Sintassi

```xml
<include file='filename' path='tagpath[@name="id"]' />
```

## <a name="parameters"></a>Parametri

- `filename`

  Nome del file XML che contiene la documentazione. Il nome file può essere qualificato con un percorso relativo al file del codice sorgente. Racchiudere `filename` tra virgolette singole (' ').

- `tagpath`

  Percorso dei tag di `filename` che porta al `name` del tag. Racchiudere il percorso tra virgolette singole (' ').

- `name`

  Identificatore del nome contenuto nel tag che precede i commenti. `name` ha sempre un `id`.

- `id`

ID del tag che precede i commenti. Racchiudere l'ID tra virgolette doppie (" ").

## <a name="remarks"></a>Osservazioni

Il `<include>` tag consente di fare riferimento ai commenti in un altro file che descrive i tipi e i membri nel codice sorgente. eliminando la necessità di inserire i commenti relativi alla documentazione direttamente nel file del codice sorgente. Inserendo la documentazione in un file separato, è possibile applicare alla documentazione il controllo del codice sorgente separatamente dal codice sorgente. Una persona, ad esempio, può avere il file di codice sorgente estratto e un'altra il file della documentazione estratto.

Il `<include>` tag utilizza la sintassi XPath XML. Per informazioni su come personalizzare l'uso, vedere la documentazione di XPath `<include>` .

## <a name="example"></a>Esempio

In questo esempio vengono presi in considerazione più file. Di seguito è riportato il primo file, che utilizza `<include>` .

[!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]

Il secondo file, *xml_include_tag. doc*, contiene i seguenti commenti alla documentazione.

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a>Output del programma

L'output seguente viene generato quando si compilano le classi Test e Test2 con la riga di comando seguente: `-doc:DocFileName.xml.`. In Visual Studio, è possibile specificare l'opzione dei commenti XML alla documentazione nel riquadro Compilazione di Creazione progetti. Quando il compilatore C# Visualizza il `<include>` tag, Cerca i commenti nella documentazione in *xml_include_tag. doc* invece che nel file di origine corrente. Il compilatore genera quindi *DocFileName. XML*e questo è il file utilizzato dagli strumenti di documentazione come [DocFX](https://dotnet.github.io/docfx/) e [Sandcastle](https://github.com/EWSoftware/SHFB) per produrre la documentazione finale.  
  
```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xml_include_tag</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)
