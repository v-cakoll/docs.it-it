### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>La proprietà CheckForOverflowUnderflow di WinForm ora è true per System.Drawing

|   |   |
|---|---|
|Dettagli|La proprietà CheckForOverflowUnderflow per l'assembly System.Drawing.dll è impostata su true.|
|Suggerimento|In precedenza, quando si verificavano overflow, il risultato veniva automaticamente troncato. Ora viene generata un'eccezione <xref:System.OverflowException?displayProperty=name>.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|

