# GESTOR-DE-PLANILLAS
### APP PLANILLAS 2024
<p>
GESTOR DE PLANILLAS 
</p>


<p>
REQUERIMIENTOS

 CREAR UNA APLICACION PARA CALCULAR EL SALARIO DE UN TRABAJADOR MENSUAL, CONTEMPLANDO DIAS TRABAJADOS 
</p>

###### Optamos por hacerlo en Csharp 
Este es parte del codigo para el calculo del salario:
public void pago()
{
    double impuesto = 0;
    double seguroSocial; 
    double horas_Trabajadas =  Convert.ToDouble(txtHoraT.Text);
    double horas_Extras = Convert.ToDouble(txtHExtras.Text);
    double salarioNeto;
    double deducciones;
    double salarioDiario;
    double horario_Normal;
    double resultado_Bruto;
    double valor_HorasExtras;
  

    salarioDiario = sueldo  / 30;
    horario_Normal = salarioDiario / 8;
    valor_HorasExtras = horario_Normal * 1.5;


    resultado_Bruto = (horas_Trabajadas * salarioDiario) + (horas_Extras * valor_HorasExtras);
 
    seguroSocial = resultado_Bruto * 0.1034;
    salarioNeto = resultado_Bruto - seguroSocial;
#### CODIGO PARA APLICAR IMPUESTO SEGUN SALARIO

    if (resultado_Bruto >= 929000 && resultado_Bruto <= 1363000)
    {
        impuesto = (1363000 - 929000) * 0.10;
        salarioNeto = (resultado_Bruto - impuesto) - seguroSocial;

    }
    else if (resultado_Bruto >= 1363000 && resultado_Bruto <= 2392000)
    {
        impuesto = (2392000 - 1363000) * 0.15;
        salarioNeto = (resultado_Bruto - impuesto) - seguroSocial;
    }
    else if (resultado_Bruto >= 2392000 && resultado_Bruto <= 4783000)
    {
        impuesto = (4783000 - 2392000) * 0.2;
        salarioNeto = (resultado_Bruto - impuesto) - seguroSocial;
    }
    else if (resultado_Bruto < 4783000)
    {
        impuesto = 0.25;
        salarioNeto = (resultado_Bruto - impuesto) - seguroSocial;
    }

    deducciones = impuesto + seguroSocial;

    txtSxBruto.Text = resultado_Bruto.ToString();
    txtSalario.Text = salarioNeto.ToString();
    txtDeducciones.Text = deducciones.ToString() ;

}



