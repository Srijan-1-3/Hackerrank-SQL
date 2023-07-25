SELECT H.hacker_id, H.name, SUM(M.max_score) AS total_score
FROM (
    SELECT S.hacker_id, S.challenge_id, max(S.score) as max_score
    FROM Submissions S GROUP BY S.hacker_id, S.challenge_id
    ) M
JOIN Hackers H ON H.hacker_id = M.hacker_id
GROUP BY H.hacker_id, H.name
HAVING total_score > 0
ORDER BY total_score DESC, H.hacker_id ASC;
