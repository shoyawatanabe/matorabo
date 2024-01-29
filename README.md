# matorabo
function simpleWordGuessingGame()
    disp('--- 単語当てゲーム ---');
    
    # 単語リスト
    単語リスト = {'リンゴ', 'バナナ', 'オレンジ', 'ブドウ', 'スイカ', 'キウイ', 'パイナップル', 'イチゴ'};
    
    # ゲームループ
    while true
        # ランダムに単語を選択
        targetWord = wordList{randi(length(wordList))};
        
        disp('新しい単語が選ばれました！');
        
        # ユーザーの入力を受け付け
        guess = input('単語を入力してください (exitで終了): ', 's');
        
        # ゲーム終了の条件
        if strcmpi(guess, 'exit')
            disp('ゲームを終了します。');
            break;
        end
        
        # 入力の検証
        if ~ischar(guess)
            disp('入力エラー: 文字列を入力してください。');
            continue;
        end
        
        # 結果の表示
        if strcmpi(guess, targetWord) #単語が当たれば
            disp(['おめでとうございます！"', targetWord, '"を当てました！']);
        else #それ以外なら
            disp(['残念！正解は"', targetWord, '"でした。もう一度挑戦してください。']);
        end
    end
end
