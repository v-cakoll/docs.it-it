---
title: Marshalling predefinito per le matrici
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
ms.openlocfilehash: f0094ac572834b2cf0d74fb53c94877da55669e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181454"
---
# <a name="default-marshaling-for-arrays"></a>Marshalling predefinito per le matrici
In un'applicazione costituita interamente da codice gestito Common Language Runtime passa i tipi di matrice come parametri In/Out. Il gestore di marshalling di interoperabilità invece passa una matrice come parametro In per impostazione predefinita.  
  
 Con l'[ottimizzazione del blocco](copying-and-pinning.md), può sembrare che una matrice copiabile da BLT funzioni come parametro In/Out quando interagisce con oggetti nello stesso apartment. Se tuttavia in seguito si esporta il codice in una libreria dei tipi usata per generare il proxy tra computer e la libreria viene usata per effettuare il marshalling delle chiamate tra gli apartment, le chiamate possono ripristinare il vero e proprio comportamento del parametro In.  
  
 Le matrici sono complesse per natura e le distinzioni tra matrici gestite e non gestite richiedono più informazioni degli altri tipi non copiabili da BLT.  
  
## <a name="managed-arrays"></a>Matrici gestite  
 I tipi di matrici gestite possono variare, ma la classe <xref:System.Array?displayProperty=nameWithType> è la classe base di tutti i tipi di matrici. La classe **System.Array** ha proprietà per determinare priorità, lunghezza e limiti inferiori e superiori di una matrice, oltre a metodi per accedere, ordinare, cercare, copiare e creare matrici.  
  
 Questi tipi di matrici sono dinamici e non devono avere un tipo statico corrispondente definito nella libreria di classi base. È utile considerare ogni combinazione di tipo di elemento e priorità come un tipo distinto di matrice. Una matrice unidimensionale di integer è quindi di un tipo diverso da una matrice unidimensionale di tipi double. Analogamente una matrice bidimensionale di integer è diversa da una matrice unidimensionale di integer. I limiti della matrice non vengono considerati quando si confrontano i tipi.  
  
 Come illustra la tabella seguente, tutte le istanze di una matrice gestita devono essere di uno specifico tipo di elemento, priorità e limite inferiore.  
  
|Tipo di matrice gestita|Tipo di elemento|Rank|Limite inferiore|Notazione della firma|  
|------------------------|------------------|----------|-----------------|------------------------|  
|**ELEMENT_TYPE_ARRAY**|Specificato dal tipo.|Specificata dalla priorità.|Specificato facoltativamente dai limiti.|*tipo* **[** *n*,*m* **]**|  
|**ELEMENT_TYPE_CLASS**|Unknown|Unknown|Unknown|**System.Array**|  
|**ELEMENT_TYPE_SZARRAY**|Specificato dal tipo.|1|0|*tipo* **[** *n* **]**|  
  
## <a name="unmanaged-arrays"></a>Matrici non gestite  
 Le matrici non gestite sono matrici protette di tipo COM o matrici di tipo C con lunghezza fissa o variabile. Le matrici protette sono matrici autodescrittive che contengono il tipo, la priorità e i limiti dei dati della matrice associati. Le matrici di tipo C sono matrici tipizzate unidimensionali con un limite inferiore fisso pari a 0. Il servizio di marshalling ha un supporto limitato per entrambi i tipi di matrici.  
  
## <a name="passing-array-parameters-to-net-code"></a>Passaggio dei parametri delle matrici al codice .NET  
 Sia le matrici di tipo C che le matrici protette possono essere passate al codice .NET dal codice non gestito come matrice protetta o matrice di tipo C. La tabella seguente illustra il valore del tipo non gestito e il tipo importato.  
  
|Tipo non gestito|Tipo importato|  
|--------------------|-------------------|  
|**SafeArray(** *Tipo* **)**|**ELEMENT_TYPE_SZARRAY** **\<** *ConvertitoTipo***>**<br /><br /> Priorità = 1, limite inferiore = 0. La dimensione è nota solo se specificata nella firma gestita. Non è possibile effettuare il marshalling delle matrici protette che non hanno priorità = 1 o limite inferiore = 0 come **SZARRAY**.|  
|*Tipo*  **[]**|**ELEMENT_TYPE_SZARRAY** **\<** *ConvertitoTipo***>**<br /><br /> Priorità = 1, limite inferiore = 0. La dimensione è nota solo se specificata nella firma gestita.|  
  
### <a name="safe-arrays"></a>Matrici protette  
 Quando una matrice protetta viene importata da una libreria dei tipi in un assembly .NET, la matrice viene convertita in una matrice unidimensionale di tipo noto (ad esempio, **int**). Le stesse regole di conversione del tipo applicate ai parametri si applicano anche agli elementi della matrice. Una matrice protetta di tipi **BSTR**, ad esempio, diventa una matrice gestita di stringhe e una matrice protetta di varianti diventa una matrice gestita di oggetti. Il tipo di elemento **SAFEARRAY** viene acquisito dalla libreria dei tipi e salvato nel valore **SAFEARRAY** dell'enumerazione <xref:System.Runtime.InteropServices.UnmanagedType>.  
  
 Poiché la priorità e i limiti della matrice protetta non possono essere determinati dalla libreria dei tipi, si presuppone che la priorità sia pari a 1 e che il limite inferiore sia pari a 0. La priorità e i limiti devono essere definiti nella firma gestita prodotta dall'[utilità di importazione della libreria dei tipi (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md). Se la priorità passata al metodo in fase di esecuzione è diversa, viene generata un'eccezione <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>. Se il tipo della matrice passata in fase di esecuzione è diverso, viene generata un'eccezione <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>. L'esempio seguente illustra le matrici protette nel codice gestito e non gestito.  
  
 **Firma non gestita**  
  
```cpp
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 **Firma gestita**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]
   ref String[] ar);  
```  
  
 È possibile effettuare il marshalling delle matrici protette multidimensionali, o con limiti diversi da zero, nel codice gestito se la firma del metodo prodotta da Tlbimp.exe viene modificata per indicare un tipo di elemento **ELEMENT_TYPE_ARRAY** invece di **ELEMENT_TYPE_SZARRAY**. In alternativa, è possibile usare l'opzione **/sysarray** con Tlbimp.exe per importare tutte le matrici come oggetti <xref:System.Array?displayProperty=nameWithType>. Nei casi in cui la matrice passata è multidimensionale, è possibile modificare il codice Microsoft Intermediate Language (MSIL) prodotto da Tlbimp.exe e quindi ricompilarla. Per informazioni dettagliate su come modificare il codice MSIL, vedere [Personalizzazione dei Runtime Callable Wrapper](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).  
  
### <a name="c-style-arrays"></a>Matrici di tipo C  
 Quando una matrice di tipo C viene importata da una libreria dei tipi in un assembly .NET, la matrice viene convertita in **ELEMENT_TYPE_SZARRAY**.  
  
 Il tipo di elemento della matrice è determinato dalla libreria dei tipi e mantenuto durante l'importazione. Le stesse regole di conversione applicate ai parametri si applicano anche agli elementi della matrice. Ad esempio, una matrice di tipi **LPStr** diventa una matrice di tipi **String**. Tlbimp.exe acquisisce il tipo di elemento della matrice e applica l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parametro.  
  
 Si presuppone che la priorità della matrice sia uguale a 1. Se la priorità è superiore a 1, la matrice viene sottoposta a marshalling come matrice unidimensionale in ordine column-major. Il limite inferiore è sempre uguale a 0.  
  
 Le librerie dei tipi possono contenere matrici a lunghezza fissa o variabile. Tlbimp.exe può importare solo matrici a lunghezza fissa dalle librerie dei tipi perché le librerie dei tipi sono prive delle informazioni necessarie per effettuare il marshalling delle matrici a lunghezza variabile. Con le matrici a lunghezza fissa, la dimensione viene importata dalla libreria dei tipi e acquisita in **MarshalAsAttribute** che viene applicato al parametro.  
  
 È necessario definire manualmente le librerie dei tipi contenenti le matrici a lunghezza variabile, come illustrato nell'esempio seguente.  
  
 **Firma non gestita**  
  
```cpp
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 **Firma gestita**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 Anche se è possibile applicare gli attributi **size_is** o **length_is** a una matrice nell'origine Interface Definition Language (IDL) per comunicare la dimensione a un client, il compilatore Microsoft Interface Definition Language (MIDL) non propaga tali informazioni alla libreria dei tipi. Senza conoscere la dimensione, il servizio di marshalling di interoperabilità non può effettuare il marshalling degli elementi della matrice. Di conseguenza, le matrici a lunghezza variabile vengono importate come argomenti di riferimento. Ad esempio:  
  
 **Firma non gestita**  
  
```cpp
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 **Firma gestita**  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
```  
  
```csharp  
void New1(ref int ar);
void New2(ref double ar);
void New3(ref String ar);
```  
  
 Per fornire al gestore di marshalling la dimensione della matrice, è possibile modificare il codice Microsoft Intermediate Language (MSIL) prodotto da Tlbimp.exe e quindi ricompilarlo. Per informazioni dettagliate su come modificare il codice MSIL, vedere [Personalizzazione dei Runtime Callable Wrapper](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)). Per indicare il numero di elementi della matrice, applicare il tipo <xref:System.Runtime.InteropServices.MarshalAsAttribute> al parametro matrice della definizione di metodo gestito in uno dei modi seguenti:  
  
- Identificare un altro parametro che contiene il numero di elementi nella matrice. I parametri vengono identificati in base alla posizione, considerando il primo parametro come numero 0.
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       \<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
- Definire la dimensione della matrice come costante. Ad esempio:  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 Quando si effettua il marshalling delle matrici dal codice non gestito al codice gestito, il gestore di marshalling controlla **MarshalAsAttribute** associato al parametro per determinare la dimensione della matrice. Se la dimensione della matrice non viene specificata, viene effettuato il marshalling di un solo elemento.  
  
> [!NOTE]
> **MarshalAsAttribute** non ha effetto sul marshalling delle matrici gestite al codice non gestito. In tal senso, la dimensione della matrice viene determinata con un'analisi. Non è possibile effettuare il marshalling di un subset di una matrice gestita.  
  
 Il gestore di marshalling di interoperabilità usa i metodi **CoTaskMemAlloc** e **CoTaskMemFree** per allocare e recuperare la memoria. Anche l'allocazione della memoria eseguita dal codice non gestito deve usare questi metodi.  
  
## <a name="passing-arrays-to-com"></a>Passaggio di matrici a COM  
 Tutti i tipi di matrici gestite possono essere passati al codice non gestito dal codice gestito. A seconda del tipo gestito e degli attributi applicati, la matrice è accessibile come matrice protetta o matrice di tipo C, come illustrato nella tabella seguente.  
  
|Tipo di matrice gestita|Esportato come|  
|------------------------|-----------------|  
|**tipo di ELEMENT_TYPE_SZARRAY** **\<** *type***>**|<xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Il tipo viene specificato nella firma. La priorità è sempre 1, il limite inferiore è sempre 0. La dimensione è sempre nota in fase di esecuzione.|  
|**ELEMENT_TYPE_ARRAY** **\<** *tipo* **>** **\<** **\<** di *rango* **>**[ *limiti* **>**]|**UnmanagedType.SafeArray(** *type* **)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Tipo, priorità e limiti vengono specificati nella firma. La dimensione è sempre nota in fase di esecuzione.|  
|**ELEMENT_TYPE_CLASS****\<**<xref:System.Array?displayProperty=nameWithType>**>**|**UT_Interface**<br /><br /> **UnmanagedType.SafeArray(** *type* **)**<br /><br /> Tipo, priorità, limite e dimensione sono sempre noti in fase di esecuzione.|  
  
 Nell'automazione OLE esiste una limitazione relativa alle matrici di strutture contenenti LPSTR o LPWSTR.  È quindi necessario effettuare il marshalling dei campi **String** come **UnmanagedType.BSTR**. In caso contrario, verrà generata un'eccezione.  
  
### <a name="element_type_szarray"></a>ELEMENT_TYPE_SZARRAY  
 Quando un metodo contenente un parametro **ELEMENT_TYPE_SZARRAY** (matrice unidimensionale) viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un elemento **SAFEARRAY** di un determinato tipo. Le stesse regole di conversione si applicano ai tipi di elementi della matrice. I contenuti della matrice gestita vengono automaticamente copiati dalla memoria gestita in **SAFEARRAY**. Ad esempio:  
  
#### <a name="managed-signature"></a>Firma gestita  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a>Firma non gestita  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 La priorità delle matrici protette è sempre 1 e il limite inferiore è sempre 0. La dimensione viene determinata in fase di esecuzione dalla dimensione della matrice gestita che viene passata.  
  
 È anche possibile effettuare il marshalling della matrice come matrice di tipo C usando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>. Ad esempio:  
  
#### <a name="managed-signature"></a>Firma gestita  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=
   UnmanagedType.LPStr, SizeParamIndex=1)]
   String [] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a>Firma non gestita  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(BSTR ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 Anche se gestore di marshalling ha le informazioni sulla lunghezza necessarie per effettuare il marshalling della matrice, la lunghezza della matrice viene in genere passata come argomento separato per comunicare la lunghezza al computer chiamato.  
  
### <a name="element_type_array"></a>ELEMENT_TYPE_ARRAY  
 Quando un metodo contenente un parametro **ELEMENT_TYPE_ARRAY** viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un elemento **SAFEARRAY** di un determinato tipo. I contenuti della matrice gestita vengono automaticamente copiati dalla memoria gestita in **SAFEARRAY**. Ad esempio:  
  
#### <a name="managed-signature"></a>Firma gestita  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a>Firma non gestita  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 Priorità, dimensione e limiti delle matrici protette vengono determinati in fase di esecuzione dalle caratteristiche della matrice gestita.  
  
 È anche possibile effettuare il marshalling della matrice come matrice di tipo C applicando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>. Ad esempio:  
  
#### <a name="managed-signature"></a>Firma gestita  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]
   String [,] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a>Firma non gestita  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 Non è possibile effettuare il marshalling di matrici annidate. La firma seguente, ad esempio, genera un errore quando viene esportata con l'[utilità di esportazione della libreria dei tipi (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).  
  
#### <a name="managed-signature"></a>Firma gestita  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="element_type_class-systemarray"></a>ELEMENT_TYPE_CLASS \<System.Array>  
 Quando un metodo contenente un parametro <xref:System.Array?displayProperty=nameWithType> viene esportato da un assembly .NET a una libreria dei tipi, il parametro matrice viene convertito in un'interfaccia **_Array**. I contenuti della matrice gestita sono accessibili solo tramite i metodi e le proprietà dell'interfaccia **_Array**. È anche possibile effettuare il marshalling di **System.Array** come **SAFEARRAY** usando l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute>. Se sottoposti a marshalling come matrice protetta, gli elementi della matrice vengono sottoposti a marshalling come varianti. Ad esempio:  
  
#### <a name="managed-signature"></a>Firma gestita  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a>Firma non gestita  
  
```cpp
HRESULT New([in] _Array *ar);
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a>Matrici all'interno di strutture  
 Le strutture non gestite possono contenere matrici incorporate. Per impostazione predefinita, viene effettuato il marshalling di questi campi di matrici incorporate come SAFEARRAY. Nell'esempio seguente `s1` è una matrice incorporata che viene allocata direttamente nella struttura stessa.  
  
#### <a name="unmanaged-representation"></a>Rappresentazione non gestita  
  
```cpp
struct MyStruct {  
    short s1[128];  
}  
```  
  
 È possibile effettuare il marshalling delle matrici come <xref:System.Runtime.InteropServices.UnmanagedType>. A questo scopo è necessario impostare il campo <xref:System.Runtime.InteropServices.MarshalAsAttribute>. La dimensione può essere impostata solo come costante. Il codice seguente mostra la definizione gestita corrispondente di `MyStruct`.  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Comportamento di marshalling predefinito](default-marshaling-behavior.md)
- [Tipi copiabili e non copiabili](blittable-and-non-blittable-types.md)
- [Attributi direzionali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [copia e blocco](copying-and-pinning.md)
