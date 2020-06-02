---
title: Elaborazione del file XML (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- XML processing [C#]
- XML [C#], processing
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
ms.openlocfilehash: 1e3d96f9398f2c08ed715111f01987e2d1948439
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287259"
---
# <a name="process-the-xml-file-c-programming-guide"></a>Elaborare il file XML (Guida per programmatori C#)

Il compilatore genera una stringa ID per ogni costrutto nel codice contrassegnato per generare la documentazione. Per informazioni su come contrassegnare il codice, vedere [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md). La stringa ID identifica in modo univoco il costrutto. I programmi che elaborano il file XML possono utilizzare la stringa ID per identificare i metadati .NET corrispondenti o l'elemento di Reflection a cui si applica la documentazione.

## <a name="id-strings"></a>Stringhe ID

Il file XML non è una rappresentazione gerarchica del codice. Si tratta di un elenco semplice con un ID generato per ogni elemento.

Per generare gli ID, il compilatore applica le regole seguenti:

- Assenza di spazi vuoti nella stringa.

- La prima parte della stringa identifica il tipo di membro usando un singolo carattere seguito da due punti. Vengono usati i tipi di membri seguenti:

    |Carattere|Tipo di membro|Note|
    |---------------|-----------------|-|
    |N|namespace|Non è possibile aggiungere a uno spazio dei nomi commenti relativi alla documentazione, ma, se supportati, è possibile creare riferimenti cref a tali commenti.|
    |T|type|Un tipo può essere una classe, un'interfaccia, una struttura, un'enumerazione o un delegato.|
    |F|campo|
    |P|proprietà|Include gli indicizzatori o altre proprietà indicizzate.|
    |M|method|Include metodi speciali, ad esempio costruttori e operatori.|
    |E|event|
    |!|stringa di errore|Nella parte restante della stringa vengono fornite informazioni sull'errore. Il compilatore C# genera informazioni sugli errori per tutti i collegamenti che non è possibile risolvere.|

- La seconda parte della stringa identifica il nome completo dell'elemento, a partire dalla radice dello spazio dei nomi. Il nome dell'elemento, i tipi di inclusione e lo spazio dei nomi sono separati da punti. Se il nome dell'elemento contiene dei punti, questi verranno sostituiti con il segno di cancelletto ('#'), Si presuppone che nessun elemento abbia un segno di hash direttamente nel nome. Ad esempio, il nome completo del costruttore di stringa è "System. String. #ctor".

- Per le proprietà e i metodi, l'elenco di parametri racchiuso tra parentesi segue. Se non sono presenti parametri, non è presente alcuna parentesi. I parametri sono separati da virgole. La codifica di ogni parametro segue direttamente il modo in cui viene codificata in una firma .NET:

  - Tipi di base. I tipi regolari (ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE) vengono rappresentati con il nome completo del tipo.

  - I tipi intrinseci, ad esempio ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF e ELEMENT_TYPE_VOID, sono rappresentati come nome completo del tipo completo corrispondente. ad esempio System.Int32 o System.TypedReference.

  - ELEMENT_TYPE_PTR viene rappresentato con '\*' dopo il tipo modificato.

  - ELEMENT_TYPE_BYREF viene rappresentato con "\@" dopo il tipo modificato.

  - ELEMENT_TYPE_PINNED viene rappresentato con '^' dopo il tipo modificato. Non viene mai generato dal compilatore C#.

  - ELEMENT_TYPE_CMOD_REQ viene rappresentato con '&#124;' seguito dal nome completo della classe di modificatori dopo il tipo modificato. Non viene mai generato dal compilatore C#.

  - ELEMENT_TYPE_CMOD_OPT viene rappresentato con '!' seguito dal nome completo della classe di modificatori dopo il tipo modificato.

  - ELEMENT_TYPE_SZARRAY viene rappresentato con "[]" dopo il tipo di elemento della matrice.

  - ELEMENT_TYPE_GENERICARRAY viene rappresentato con "[?]" dopo il tipo di elemento della matrice. Non viene mai generato dal compilatore C#.

  - ELEMENT_TYPE_ARRAY è rappresentato come [*lowerbound*: `size` ,*lowerbound*: `size` ] dove il numero di virgole è il rango-1 e i limiti inferiori e le dimensioni di ogni dimensione, se noti, sono rappresentati in decimali. Se non si specifica una dimensione o un limite inferiore, viene omesso. Se vengono omessi il limite inferiore e la dimensione per una dimensione specifica, viene omesso anche ':'. Ad esempio, una matrice a due dimensioni con limiti inferiori pari a 1 e dimensioni non specificate viene rappresentata con [1:,1:].

  - ELEMENT_TYPE_FNPTR viene rappresentato con "=FUNC:`type`(*signature*)", dove `type` rappresenta il tipo restituito e *signature* identifica gli argomenti del metodo. Se non vi sono argomenti, le parentesi vengono omesse. Non viene mai generato dal compilatore C#.

  I componenti della firma seguenti non sono rappresentati perché non vengono usati per distinguere i metodi di overload:

  - convenzione di chiamata

  - tipo restituito

  - ELEMENT_TYPE_SENTINEL

- Solo per gli operatori di conversione ( `op_Implicit` e `op_Explicit` ), il valore restituito del metodo viene codificato come ' ~' seguito dal tipo restituito.

- Nel caso di tipi generici, il nome del tipo è seguito da un apice inverso e quindi da un numero che indica il numero di parametri di tipo generici. Ad esempio:

     ``<member name="T:SampleClass`2">`` è il tag di un tipo che viene definito come `public class SampleClass<T, U>`.

     Per i metodi che accettano tipi generici come parametri, i parametri di tipo generico vengono specificati come numeri preceduti da un apice inverso (ad esempio \` , 0, \` 1). Ogni numero rappresenta una notazione di matrice in base zero per i parametri generici del tipo.

## <a name="examples"></a>Esempi

Negli esempi seguenti viene illustrato come vengono generate le stringhe ID per una classe e i relativi membri:

[!code-csharp[csProgGuidePointers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#21)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [-DOC (opzioni del compilatore C#)](../../language-reference/compiler-options/doc-compiler-option.md)
- [Commenti relativi alla documentazione XML](./index.md)
