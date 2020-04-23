---
title: Marshalling predefinito per gli oggetti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
ms.openlocfilehash: e0de715a3ed33eedf212fc3e0e9930c9cbaa0a38
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123582"
---
# <a name="default-marshaling-for-objects"></a>Marshalling predefinito per gli oggetti

I parametri e i campi tipizzati come <xref:System.Object?displayProperty=nameWithType> possono essere esposti al codice non gestito come uno dei tipi seguenti:

- Una variante quando l'oggetto è un parametro.

- Un'interfaccia quando l'oggetto è un campo della struttura.

Solo l'interoperabilità COM supporta il marshalling per i tipi di oggetto. Il comportamento predefinito è il marshalling degli oggetti alle varianti COM. Queste regole si applicano solo al tipo **Object** e non agli oggetti fortemente tipizzati derivanti dalla classe **Object**.

## <a name="marshaling-options"></a>Opzioni di marshalling

La tabella seguente illustra le opzioni di marshalling per il tipo di dati **Object**. L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per effettuare il marshalling di oggetti.

|Tipo di enumerazione|Descrizione del formato non gestito|
|----------------------|-------------------------------------|
|**UnmanagedType.Struct**<br /><br /> (predefinita per i parametri)|Una variante di tipo COM.|
|**UnmanagedType.Interface**|Un'interfaccia **IDispatch**, se possibile; in caso contrario, un'interfaccia **IUnknown**.|
|**UnmanagedType.IUnknown**<br /><br /> (predefinita per i campi)|Un' interfaccia **IUnknown**.|
|**UnmanagedType.IDispatch**|Un'interfaccia **IDispatch**.|

L'esempio seguente illustra la definizione dell'interfaccia gestita per `MarshalObject`.

```vb
Interface MarshalObject
   Sub SetVariant(o As Object)
   Sub SetVariantRef(ByRef o As Object)
   Function GetVariant() As Object

   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _
      As Object)
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _
      As Object)
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object
End Interface
```

```csharp
interface MarshalObject {
   void SetVariant(Object o);
   void SetVariantRef(ref Object o);
   Object GetVariant();

   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();
}
```

Il codice seguente esporta l'interfaccia `MarshalObject` in una libreria dei tipi.

```cpp
interface MarshalObject {
   HRESULT SetVariant([in] VARIANT o);
   HRESULT SetVariantRef([in,out] VARIANT *o);
   HRESULT GetVariant([out,retval] VARIANT *o)
   HRESULT SetIDispatch([in] IDispatch *o);
   HRESULT SetIDispatchRef([in,out] IDispatch **o);
   HRESULT GetIDispatch([out,retval] IDispatch **o)
   HRESULT SetIUnknown([in] IUnknown *o);
   HRESULT SetIUnknownRef([in,out] IUnknown **o);
   HRESULT GetIUnknown([out,retval] IUnknown **o)
}
```

> [!NOTE]
> Il gestore di marshalling di interoperabilità libera automaticamente gli oggetti allocati nella variante dopo la chiamata.

L'esempio seguente illustra un tipo valore formattato.

```vb
Public Structure ObjectHolder
   Dim o1 As Object
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object
End Structure
```

```csharp
public struct ObjectHolder {
   Object o1;
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;
}
```

Il codice seguente esporta il tipo formattato in una libreria dei tipi.

```cpp
struct ObjectHolder {
   VARIANT o1;
   IDispatch *o2;
}
```

## <a name="marshaling-object-to-interface"></a>Marshalling dell'oggetto all'interfaccia

Quando un oggetto viene esposto a COM come interfaccia, tale interfaccia è l'interfaccia di classe del tipo gestito <xref:System.Object> (interfaccia **_Object**). Questa interfaccia è tipizzata come **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) o **IUnknown** (**UnmanagedType. IUnknown**) nella libreria dei tipi risultante. I client COM possono richiamare in modo dinamico i membri della classe gestita o eventuali membri implementati dalle classi derivate tramite l'interfaccia **_Object**. Il client può anche chiamare **QueryInterface** per ottenere le altre interfacce implementate in modo esplicito dal tipo gestito.

## <a name="marshaling-object-to-variant"></a>Marshalling dell'oggetto alla variante

Quando viene effettuato il marshalling di un oggetto a una variante, il tipo di variante interno viene determinato in fase di esecuzione, in base alle regole seguenti:

- Se il riferimento all'oggetto è null (**Nothing** in Visual Basic), viene effettuato il marshalling dell'oggetto a una variante di tipo **VT_EMPTY**.

- Se l'oggetto è un'istanza di un tipo elencato nella tabella seguente, il tipo di variante risultante viene determinato dalle regole incluse nel gestore di marshalling e visualizzate nella tabella.

- Gli altri oggetti che devono controllare in modo esplicito il comportamento di marshalling possono implementare l'interfaccia <xref:System.IConvertible>. In tal caso, il tipo di variante viene determinato dal codice del tipo restituito dal metodo <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>. In caso contrario, viene effettuato il marshalling dell'oggetto come variante di tipo **VT_UNKNOWN**.

### <a name="marshaling-system-types-to-variant"></a>Marshalling di tipi di sistema alla variante

La tabella seguente illustra i tipi di oggetto gestito e i corrispondenti tipi di varianti COM. Questi tipi vengono convertiti solo quando la firma del metodo chiamato è di tipo <xref:System.Object?displayProperty=nameWithType>.

|Tipo oggetto|Tipo di variante COM|
|-----------------|----------------------|
|Riferimento all'oggetto null (**Nothing** in Visual Basic).|**VT_EMPTY**|
|<xref:System.DBNull?displayProperty=nameWithType>|**VT_NULL**|
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|**VT_ERROR**|
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|**VT_ERROR** con **E_PARAMNOTFOUND**|
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|**VT_DISPATCH**|
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|**VT_UNKNOWN**|
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|**VT_CY**|
|<xref:System.Boolean?displayProperty=nameWithType>|**VT_BOOL**|
|<xref:System.SByte?displayProperty=nameWithType>|**VT_I1**|
|<xref:System.Byte?displayProperty=nameWithType>|**VT_UI1**|
|<xref:System.Int16?displayProperty=nameWithType>|**VT_I2**|
|<xref:System.UInt16?displayProperty=nameWithType>|**VT_UI2**|
|<xref:System.Int32?displayProperty=nameWithType>|**VT_I4**|
|<xref:System.UInt32?displayProperty=nameWithType>|**VT_UI4**|
|<xref:System.Int64?displayProperty=nameWithType>|**VT_I8**|
|<xref:System.UInt64?displayProperty=nameWithType>|**VT_UI8**|
|<xref:System.Single?displayProperty=nameWithType>|**VT_R4**|
|<xref:System.Double?displayProperty=nameWithType>|**VT_R8**|
|<xref:System.Decimal?displayProperty=nameWithType>|**VT_DECIMAL**|
|<xref:System.DateTime?displayProperty=nameWithType>|**VT_DATE**|
|<xref:System.String?displayProperty=nameWithType>|**VT_BSTR**|
|<xref:System.IntPtr?displayProperty=nameWithType>|**VT_INT**|
|<xref:System.UIntPtr?displayProperty=nameWithType>|**VT_UINT**|
|<xref:System.Array?displayProperty=nameWithType>|**VT_ARRAY**|

Usando l'interfaccia `MarshalObject` definita nell'esempio precedente, l'esempio di codice seguente illustra come passare diversi tipi di varianti a un server COM.

```vb
Dim mo As New MarshalObject()
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.
```

```csharp
MarshalObject mo = new MarshalObject();
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.
```

È possibile effettuare il marshalling dei tipi COM privi di tipi gestiti corrispondenti usando classi wrapper, ad esempio <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper> e <xref:System.Runtime.InteropServices.CurrencyWrapper>. L'esempio di codice seguente illustra come usare questi wrapper per passare diversi tipi di varianti a un server COM.

```vb
Imports System.Runtime.InteropServices
' Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(New UnknownWrapper(inew))
' Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(New DispatchWrapper(inew))
' Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(New ErrorWrapper(&H80054002))
' Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))
```

```csharp
using System.Runtime.InteropServices;
// Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(new UnknownWrapper(inew));
// Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(new DispatchWrapper(inew));
// Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(new ErrorWrapper(0x80054002));
// Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));
```

Le classi wrapper vengono definite nello spazio dei nomi <xref:System.Runtime.InteropServices>.

### <a name="marshaling-the-iconvertible-interface-to-variant"></a>Marshalling dell'interfaccia IConvertible alla variante

I tipi diversi da quelli elencati nella sezione precedente possono controllare come viene effettuato il marshalling implementando l'interfaccia <xref:System.IConvertible>. Se l'oggetto implementa l'interfaccia **IConvertible**, il tipo di variante COM viene determinato in fase di esecuzione dal valore dell'enumerazione <xref:System.TypeCode> restituita dal metodo <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.

La tabella seguente illustra i possibili valori per l'enumerazione **TypeCode** e il tipo di variante COM corrispondente per ogni valore.

|TypeCode|Tipo di variante COM|
|--------------|----------------------|
|**TypeCode.Empty**|**VT_EMPTY**|
|**TypeCode.Object**|**VT_UNKNOWN**|
|**TypeCode.DBNull**|**VT_NULL**|
|**TypeCode.Boolean**|**VT_BOOL**|
|**TypeCode.Char**|**VT_UI2**|
|**TypeCode.Sbyte**|**VT_I1**|
|**TypeCode.Byte**|**VT_UI1**|
|**TypeCode.Int16**|**VT_I2**|
|**TypeCode.UInt16**|**VT_UI2**|
|**TypeCode.Int32**|**VT_I4**|
|**TypeCode.UInt32**|**VT_UI4**|
|**TypeCode.Int64**|**VT_I8**|
|**TypeCode.UInt64**|**VT_UI8**|
|**TypeCode.Single**|**VT_R4**|
|**TypeCode.Double**|**VT_R8**|
|**TypeCode.Decimal**|**VT_DECIMAL**|
|**TypeCode.DateTime**|**VT_DATE**|
|**TypeCode.String**|**VT_BSTR**|
|Non supportato.|**VT_INT**|
|Non supportato.|**VT_UINT**|
|Non supportato.|**VT_ARRAY**|
|Non supportato.|**VT_RECORD**|
|Non supportato.|**VT_CY**|
|Non supportato.|**VT_VARIANT**|

Il valore della variante COM viene determinato chiamando l'interfaccia **IConvertible.To** *Type*, dove **To** *Type* è la routine di conversione che corrisponde al tipo restituito da **IConvertible.GetTypeCode**. Ad esempio, il marshalling di un oggetto che restituisce **TypeCode.Double** da **IConvertible.GetTypeCode** viene effettuato come variante COM di tipo **VT_R8**. Per ottenere il valore della variante (archiviata nel campo **dblVal** della variante COM), è possibile eseguire il cast all'interfaccia **IConvertible** e chiamare il metodo <xref:System.IConvertible.ToDouble%2A>.

## <a name="marshaling-variant-to-object"></a>Marshalling della variante all'oggetto

Quando si effettua il marshalling di una variante a un oggetto, il tipo e a volte il valore della variante di cui viene effettuato il marshalling determinano il tipo dell'oggetto prodotto. La tabella seguente identifica tale tipo di variante e il tipo di oggetto corrispondente creato dal gestore di marshalling quando una variante viene passata da COM a .NET Framework.

|Tipo di variante COM|Tipo oggetto|
|----------------------|-----------------|
|**VT_EMPTY**|Riferimento all'oggetto null (**Nothing** in Visual Basic).|
|**VT_NULL**|<xref:System.DBNull?displayProperty=nameWithType>|
|**VT_DISPATCH**|**System.__ComObject** o null se (pdispVal == null)|
|**VT_UNKNOWN**|**System.__ComObject** o null se (punkVal == null)|
|**VT_ERROR**|<xref:System.UInt32?displayProperty=nameWithType>|
|**VT_BOOL**|<xref:System.Boolean?displayProperty=nameWithType>|
|**VT_I1**|<xref:System.SByte?displayProperty=nameWithType>|
|**VT_UI1**|<xref:System.Byte?displayProperty=nameWithType>|
|**VT_I2**|<xref:System.Int16?displayProperty=nameWithType>|
|**VT_UI2**|<xref:System.UInt16?displayProperty=nameWithType>|
|**VT_I4**|<xref:System.Int32?displayProperty=nameWithType>|
|**VT_UI4**|<xref:System.UInt32?displayProperty=nameWithType>|
|**VT_I8**|<xref:System.Int64?displayProperty=nameWithType>|
|**VT_UI8**|<xref:System.UInt64?displayProperty=nameWithType>|
|**VT_R4**|<xref:System.Single?displayProperty=nameWithType>|
|**VT_R8**|<xref:System.Double?displayProperty=nameWithType>|
|**VT_DECIMAL**|<xref:System.Decimal?displayProperty=nameWithType>|
|**VT_DATE**|<xref:System.DateTime?displayProperty=nameWithType>|
|**VT_BSTR**|<xref:System.String?displayProperty=nameWithType>|
|**VT_INT**|<xref:System.Int32?displayProperty=nameWithType>|
|**VT_UINT**|<xref:System.UInt32?displayProperty=nameWithType>|
|**VT_ARRAY** &#124; **VT_**\*|<xref:System.Array?displayProperty=nameWithType>|
|**VT_CY**|<xref:System.Decimal?displayProperty=nameWithType>|
|**VT_RECORD**|Tipo valore boxed corrispondente.|
|**VT_VARIANT**|Non supportato.|

I tipi di variante passati da COM al codice gestito e quindi di nuovo a COM potrebbero non conservare lo stesso tipo di variante per tutta la durata della chiamata. Si consideri che cosa accade quando una variante di tipo **VT_DISPATCH** viene passata da COM a .NET Framework. Durante il marshalling, la variante viene convertita in <xref:System.Object?displayProperty=nameWithType>. Se **Object** viene quindi passato nuovamente a COM, ne viene effettuato il marshalling a una variante di tipo **VT_UNKNOWN**. Non esiste garanzia che la variante prodotta quando viene effettuato il marshalling di un oggetto dal codice gestito a COM sarà dello stesso tipo della variante usata inizialmente per produrre l'oggetto.

## <a name="marshaling-byref-variants"></a>Marshalling di varianti ByRef

Anche se le varianti in sé possono essere passate in base al valore o al riferimento, è anche possibile usare il flag **VT_BYREF** con qualsiasi variante per indicare che i contenuti della variante verranno passati in base al riferimento invece che al valore. La differenza tra il marshalling delle varianti in base al riferimento e il marshalling di una variante con il flag **VT_BYREF** impostato può risultare poco chiara. La figura seguente illustra le differenze:

![Diagramma che illustra la variante passata allo stack.](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)
Varianti passate per valore e per riferimento

**Comportamento predefinito per il marshalling di oggetti e varianti per valore**

- Quando si passano gli oggetti dal codice gestito a COM, i contenuti dell'oggetto vengono copiati in una nuova variante creata dal gestore di marshalling, usando le regole definite in [Marshalling dell'oggetto alla variante](#marshaling-object-to-variant). Le modifiche apportate alla variante sul lato non gestito non vengono propagate all'oggetto originale al ritorno dalla chiamata.

- Quando si passano le varianti da COM al codice gestito, i contenuti della variante vengono copiati in un nuovo oggetto creato, usando le regole definite in [Marshalling della variante all'oggetto](#marshaling-variant-to-object). Le modifiche apportate all'oggetto sul lato gestito non vengono propagate alla variante originale al ritorno dalla chiamata.

**Comportamento predefinito per il marshalling di oggetti e varianti per riferimento**

Per propagare le modifiche al chiamante, i parametri devono essere passati per riferimento. È ad esempio possibile usare la parola chiave **ref** in C# (o **ByRef** nel codice gestito di Visual Basic) per passare i parametri per riferimento. In COM i parametri per riferimento vengono passati usando un puntatore, ad esempio una **variante \***.

- Quando si passa un oggetto a COM per riferimento, il gestore di marshalling crea una nuova variante e copia i contenuti del riferimento all'oggetto nella variante prima che venga effettuata la chiamata. La variante viene passata alla funzione non gestita in cui l'utente può modificare i contenuti della variante. Al ritorno dalla chiamata, le modifiche apportate alla variante sul lato non gestito vengono propagate all'oggetto originale. Se il tipo della variante è diverso dal tipo della variante passata alla chiamata, le modifiche vengono propagate a un oggetto di tipo diverso, ovvero il tipo dell'oggetto passato nella chiamata può essere diverso dal tipo dell'oggetto restituito dalla chiamata.

- Quando si passa una variante al codice gestito per riferimento, il gestore di marshalling crea un nuovo oggetto e copia i contenuti della variante nell'oggetto prima di effettuare la chiamata. Un riferimento all'oggetto viene passato alla funzione non gestita, in cui l'utente può modificare l'oggetto. Al ritorno dalla chiamata, le modifiche apportate all'oggetto di riferimento vengono propagate alla variante originale. Se il tipo dell'oggetto è diverso dal tipo dell'oggetto passato alla chiamata, il tipo della variante originale viene modificato e il valore viene propagato nella variante. Anche in questo caso il tipo della variante passata nella chiamata può essere diverso dal tipo della variante restituita dalla chiamata.

 **Comportamento predefinito per il marshalling di una variante con il flag VT_BYREF impostato**

- Una variante che viene passata al codice gestito per valore può avere il flag **VT_BYREF** impostato per indicare che la variante contiene un riferimento invece che un valore. In questo caso, viene ancora effettuato il marshalling della variante a un oggetto perché la variante verrà passata per valore. Il gestore di marshalling dereferenzia automaticamente i contenuti della variante e la copia in un nuovo oggetto creato prima di eseguire la chiamata. L'oggetto viene quindi passato nella funzione gestita, tuttavia, al ritorno dalla chiamata, l'oggetto non viene propagato nella variante originale. Le modifiche apportate all'oggetto gestito vengono perse.

  > [!CAUTION]
  > Non è possibile modificare il valore di una variante passata per valore, anche se la variante ha il flag **VT_BYREF** impostato.

- Una variante che viene passata al codice gestito per riferimento può anche avere il flag **VT_BYREF** impostato per indicare che la variante contiene un altro riferimento. In questo caso, viene effettuato il marshalling della variante a un oggetto **ref** perché la variante verrà passata per riferimento. Il gestore di marshalling dereferenzia automaticamente i contenuti della variante e la copia in un nuovo oggetto creato prima di eseguire la chiamata. Al ritorno dalla chiamata, il valore dell'oggetto viene propagato al riferimento nella variante originale solo se l'oggetto è dello stesso tipo dell'oggetto passato, ovvero la propagazione non modifica il tipo di una variante con il flag **VT_BYREF** impostato. Se il tipo dell'oggetto viene modificato durante la chiamata, al ritorno dalla chiamata viene generata un'eccezione <xref:System.InvalidCastException>.

La tabella seguente riepiloga le regole di propagazione per varianti e oggetti.

|From|A|Modifiche propagate|
|----------|--------|-----------------------------|
|**Variante**  *v*|**Oggetto**  *o*|Never|
|**Oggetto**  *o*|**Variante**  *v*|Never|
|**Variante**   ***\****  *PV*|**Oggetto ref**  *o*|Sempre|
|**Oggetto Ref**  *o*|**Variante**   ***\****  *PV*|Sempre|
|**Variante**  *v* **(VT_BYREF** *&#124;* **VT_\*)**|**Oggetto**  *o*|Never|
|**Variante**  *v* **(VT_BYREF** *&#124;* **VT_)**|**Oggetto ref**  *o*|Solo se il tipo non è stato modificato.|

## <a name="see-also"></a>Vedere anche

- [Comportamento di marshalling predefinito](default-marshaling-behavior.md)
- [Tipi copiabili e non copiabili](blittable-and-non-blittable-types.md)
- [Attributi direzionali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [copia e blocco](copying-and-pinning.md)
