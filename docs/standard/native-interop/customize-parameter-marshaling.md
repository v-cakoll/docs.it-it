---
title: Personalizzazione del marshalling dei parametri - .NET
description: Informazioni su come personalizzare il modo in cui .NET effettua il marshalling dei parametri in una rappresentazione nativa.
ms.date: 01/18/2019
ms.openlocfilehash: ff646ad942cf051ce90cd75b24c8562e536182d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400365"
---
# <a name="customizing-parameter-marshaling"></a>Personalizzazione del marshalling dei parametri

Quando il comportamento di marshalling dei parametri predefinito del runtime .NET non esegue le operazioni desiderate, è possibile usare l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> per personalizzare il modo in cui viene effettuato il marshalling dei parametri.

## <a name="customizing-string-parameters"></a>Personalizzazione dei parametri stringa

.NET offre un'ampia gamma di formati per il marshalling delle stringhe. Questi metodi sono suddivisi in sezioni distinte per le stringhe in stile C e per i formati di stringa per Windows.

### <a name="c-style-strings"></a>Stringhe in stile C

Ognuno di questi formati passa una stringa con terminazione Null al codice nativo. Si differenziano per la codifica della stringa nativa.

| Valore della proprietà `System.Runtime.InteropServices.UnmanagedType` | Codifica |
|------------------------------------------------------|----------|
| LPStr | ANSI |
| LPUTF8Str | UTF-8 |
| LPWStr | UTF-16 |
| LPTStr | UTF-16 |

Il formato <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=nameWithType> è leggermente diverso. Ad esempio `LPWStr`, effettua il marshalling della stringa in una stringa in stile C nativo con codifica UTF-16. Tuttavia, la firma gestita richiede il passaggio della stringa per riferimento e la firma nativa corrispondente accetta la stringa per valore. Questa distinzione consente di usare un'API nativa che accetta una stringa per valore e la modifica sul posto senza dover usare `StringBuilder`. È consigliabile evitare di usare questo formato manualmente, perché è soggetto a creare confusione con le firme native e gestite non corrispondenti.

### <a name="windows-centric-string-formats"></a>Formati di stringa per Windows

Quando si interagisce con le interfacce COM oppure OLE, probabilmente si scoprirà che le funzioni native accettano stringhe come argomenti `BSTR`. È possibile usare il tipo non gestito <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> per effettuare il marshalling di una stringa come `BSTR`.

Se si interagisce con API WinRT, è possibile usare il formato <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> per effettuare il marshalling di una stringa come `HSTRING`.

## <a name="customizing-array-parameters"></a>Personalizzazione dei parametri di matrice

.NET offre anche vari modi per effettuare il marshalling di parametri di matrice. Se si chiama un'API che accetta una matrice in stile C, usare il tipo non gestito <xref:System.Runtime.InteropServices.UnmanagedType.LPArray?displayProperty=nameWithType>. Se i valori nella matrice richiedono il marshalling personalizzato, è possibile usare il campo <xref:System.Runtime.InteropServices.MarshalAsAttribute.ArraySubType> per l'attributo `[MarshalAs]` a tale scopo.

Se si usano API COM, probabilmente sarà necessario effettuare il marshalling dei parametri di matrice come `SAFEARRAY*`. A tale scopo, è possibile usare il tipo non gestito <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>. Il tipo predefinito degli elementi di `SAFEARRAY` è indicato nella tabella sulla [personalizzazione dei campi `object`](./customize-struct-marshaling.md#marshaling-systemobjects). È possibile usare i campi <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> e <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> per personalizzare il tipo di elemento esatto di `SAFEARRAY`.

## <a name="customizing-boolean-or-decimal-parameters"></a>Personalizzazione dei parametri booleani o decimali

Per informazioni sul marshalling dei parametri booleani o decimali, vedere [Personalizzazione del marshalling delle strutture](customize-struct-marshaling.md).

## <a name="customizing-object-parameters-windows-only"></a>Personalizzazione dei parametri oggetto (solo Windows)

In Windows, il runtime .NET offre molti modi diversi per effettuare il marshalling dei parametri oggetto in codice nativo.

### <a name="marshaling-as-specific-com-interfaces"></a>Marshalling come interfacce COM specifiche

Se l'API accetta un puntatore a un oggetto COM, è possibile usare uno dei formati `UnmanagedType` seguenti per un parametro di tipo `object` per indicare a .NET di effettuare il marshalling come queste interfacce specifiche:

- `IUnknown`
- `IDispatch`
- `IInspectable`

Inoltre, se il tipo è contrassegnato `[ComVisible(true)]` o si effettua il marshalling del tipo `object`, è possibile usare il formato <xref:System.Runtime.InteropServices.UnmanagedType.Interface?displayProperty=nameWithType> per effettuare il marshalling dell'oggetto come un COM Callable Wrapper per la visualizzazione COM del tipo.

### <a name="marshaling-to-a-variant"></a>Marshaling in `VARIANT`

Se l'API nativa richiede un `VARIANT` Win32, è possibile usare il formato <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> per il parametro `object` per effettuare il marshalling degli oggetti come `VARIANT`. Vedere la documentazione sulla [personalizzazione dei campi `object`](customize-struct-marshaling.md#marshaling-systemobjects) per informazioni sul mapping tra tipi .NET e tipi `VARIANT`.

### <a name="custom-marshalers"></a>Gestori di marshalling personalizzati

Se si vuole proiettare un'interfaccia COM nativa in un tipo gestito diverso, è possibile usare il formato `UnmanagedType.CustomMarshaler` e un'implementazione di <xref:System.Runtime.InteropServices.ICustomMarshaler> per fornire il proprio codice di marshalling personalizzato.
