Public Class Form1
    Dim A As String
    Dim B As String
    Dim C As String
    Dim Z As String
    Dim X As String
    Dim Y As String
    Dim I As String
    Dim G As String
    Dim J As String


    Private Sub TextBox1_TextChanged(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles TextBox1.TextChanged

    End Sub

    Private Sub TextBox2_TextChanged(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles TextBox2.TextChanged

    End Sub

    Private Sub TextBox3_TextChanged(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles TextBox3.TextChanged

    End Sub

    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
        If G = 0 Then
            G = G + 1
            Random()
            Picker()
        End If
        Checker()
    End Sub

    Private Sub Label1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Label1.Click

    End Sub

    Private Sub Label2_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Label2.Click

    End Sub
    Private Function Random()
        Randomize()
        A = CInt(Int(4 * Rnd()) + 1)
        B = CInt(Int(4 * Rnd()) + 1)
        C = CInt(Int(4 * Rnd()) + 1)
        Return 0
    End Function
    Private Function Picker()
        Select Case A
            Case 1
                Z = "R"
            Case 2
                Z = "V"
            Case 3
                Z = "B"
            Case 4
                Z = "J"
        End Select
        Select Case B
            Case 1
                X = "R"
            Case 2
                X = "V"
            Case 3
                X = "B"
            Case 4
                X = "J"
        End Select
        Select Case C
            Case 1
                Y = "R"
            Case 2
                Y = "V"
            Case 3
                Y = "B"
            Case 4
                Y = "J"
        End Select

        Return A
    End Function
    Private Function Checker()
        If TextBox1.Text = Z Then
            I = I + 1
        ElseIf TextBox1.Text = X Or TextBox1.Text = Y Then
            J = J + 1
        End If
        If TextBox2.Text = X Then
            I = I + 1
        ElseIf TextBox1.Text = Z Or TextBox1.Text = Y Then
            J = J + 1
        End If
        If TextBox3.Text = Y Then
            I = I + 1
        ElseIf TextBox1.Text = X Or TextBox1.Text = Z Then
            J = J + 1
        End If

        If I < 3 Then
            MsgBox("Couleur Bien :" & I & vbNewLine & "Couleur bien mais au mauvais position " & J)
        End If
        If I = 3 Then
            MsgBox("Tu Gagne!!!")
            I = 0
            J = 0
            G = 0
            TextBox1.Clear()
            TextBox2.Clear()
            TextBox3.Clear()
        End If

        If MsgBoxResult.Ok Then
            I = 0
            J = 0
        End If



        Return A
    End Function
End Class
