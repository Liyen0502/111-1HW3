# 第2次作業-作業-HW2
>
>學號：109111104
><br />
>姓名：李彥賓
><br />
>作業撰寫時間：20 (mins，包含程式撰寫時間)
><br />
>最後撰寫文件日期：2022/10/30
>

本份文件包含以下主題：(至少需下面兩項，若是有多者可以自行新增)
- [x]說明內容
- [x]個人認為完成作業須具備觀念

## 說明程式與內容

開始寫說明，該說明需說明想法，
並於之後再對上述想法的每一部分將程式進一步進行展現，
若需引用程式區則使用下面方法，
若為.cs檔內程式除了於敘述中需註明檔案名稱外，
還需使用語法` ```csharp 程式碼 ``` `，
下段程式碼則為使用後結果：

public partial class Test : System.Web.UI.Page
    {
        string[] sa_Cate = new string[2] { "蔬菜", "水果" };
        string[,] sa_Food = new string[2, 2] { { "A菜", "空心菜" }, { "番茄", "火龍果" } };
        protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                for (int i_ct = 0; i_ct < sa_Cate.Length; i_ct++)
                {
                    ListItem downlist1 = new ListItem();
                    downlist1.Text = downlist1.Value = sa_Cate[i_ct];
                    ddl_Category.Items.Add(downlist1);
                }
                mt_GenSecondList();
            }
        }
        protected void mt_GenSecondList()
        {
            int i_ind = ddl_Category.SelectedIndex;
            ddl_Food.Items.Clear();
            for (int i_Ct = 0; i_Ct < sa_Food.GetLength(1); i_Ct++)
            {
                ListItem downlist2 = new ListItem();
                downlist2.Text = downlist2.Value = sa_Food[i_ind,i_Ct];
                ddl_Food.Items.Add(downlist2);
            }
        }
        protected void ddl_Category_SelectedIndexChanged(object sender, EventArgs e)
        {
            mt_GenSecondList();
        }
    }

若要於內文中標示部分.aspx檔，則使用以下標籤` ```html 程式碼 ``` `，
下段程式碼則為使用後結果：

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
            <asp:DropDownList ID="ddl_Category" runat="server" AutoPostBack="True" OnSelectedIndexChanged="ddl_Category_SelectedIndexChanged"></asp:DropDownList>
            <asp:DropDownList ID="ddl_Food" runat="server"></asp:DropDownList>
        </div>
    </form>
</body>
</html>


## 個人認為完成作業須具備觀念

開始寫說明，需要說明本次作業個人覺得需學會那些觀念 (需寫成文章，需最少50字，
並且文內不得有你、我、他三種文字)

給予題目所需對應物件屬性，如何用程式碼寫出下拉式選單，了解IsPostBack觀念。
