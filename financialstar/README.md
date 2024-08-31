financials_origem
<br>
dax >>> = Table.TransformColumnTypes(financials_Table,{{"Segment", type text}, {"Country", type text}, {"Product", type text}, {"Discount Band", type text}, {"Units Sold", type number}, {"Manufacturing Price", Int64.Type}, {"Sale Price", Int64.Type}, {"Gross Sales", type number}, {"Discounts", type number}, {" Sales", type number}, {"COGS", type number}, {"Profit", type number}, {"Date", type date}, {"Month Number", Int64.Type}, {"Month Name", type text}, {"Year", Int64.Type}})

D_Produtos
<br>
dax >>>> = Table.ReorderColumns(#"Índice Adicionado",{"Índice", "Product", "Contagem", "Valor mínimo de venda", "Valor máximo de venda", "Mediana do valor de vendas", "Média do valor de vendas", "Média da manufatura"})

D_Descontos
<br>
dax >>>> = Table.Distinct(#"Colunas Removidas1")

F_Vendas
<br>
dax >>>> = Table.ReorderColumns(#"Colunas Removidas1",{"SK_ID", "ID_Produto", "Product", "Country", "Segment", " Sales", "Units Sold", "Sale Price", "Discount Band", "Profit", "Date", "Month Name", "Year"})

D_Produtos_Detalhes
<br>
dax >>>> = Table.RemoveColumns(#"Colunas Reordenadas",{"Product"})

D_Detalhes
<br>
dax >>>> = Table.ReorderColumns(#"Tipo Alterado",{"Product", "Country", "Segment", " Sales", "Discount Band", "Units Sold", "Manufacturing Price", "Sale Price", "Gross Sales", "Discounts", "COGS", "Profit", "Date", "Month Number", "Month Name", "Year"})
